## Requirements Analysis
The following analyses follow the format:

*Given business requirement*
  * Initial Thoughts (if any)
  * NFRs (if any)
    * NFR 1
    * NFR 2


1. *MonitorMe reads data from eight different patient-monitoring equipment vital sign input sources: heart rate, blood pressure, oxygen level, blood sugar, respiration rate, electrocardiogram (ECG), body temperature, and sleep status (sleep or awake). It then sends the data to a consolidated monitoring screen (per nurses station) with an average response time of 1 second or less. The consolidated monitoring screen displays each patients vital signs, rotating between patients every 5 seconds. There is a maximum of 20 patients per nurses station.*

   *Each patient monitoring device transmits vital sign readings at a different rate:
    Heart rate: every 500ms
    Blood pressure: every hour
    Oxygen level: every 5 seconds 
    Blood sugar: every 2 minutes 
    Respiration: every second
    ECG: every second
    Body temperature: every 5 minutes 
    Sleep status: every 2 minutes*

   *Maximum number of patients per physical MonitorMe instance: 500*
   *MonitorMe will be deployed as an on-premises system. Each physical hospital location will have its own installation of the complete MonitorMe system (including the recorded raw monitoring data).*

   * NFRs:
     * **Performance** - The system must achieve an average response time of 1 second or less for reading and displaying vital sign data on the consolidated monitoring screen. At the same time there are limits for patients per nurses station and patients per physical instance. It means we can make system scalable increasing nurses stations and instances.  
     * **Deployability** - It must be easy to install the system instances and add new nurses stations.


2. *For each vital sign, MonitorMe must record and store the past 24 hours of all vital sign readings. A medical professional can review this history, filtering on time range as well as vital sign.*

   * NFRs: 
     * **Recoverability** – The system must start where it left off in the event of a system crash without data loss.
     * **Availability** – MonitorMe uptime is critical. Human lives are at stake.


3. *In addition to recording raw monitoring data, the MonitorMe software must also analyze each patient’s vital signs and alert a medical professional if it detects an issue (e.g., decrease in oxygen level) or reaches a preset threshold (e.g., temperature has reached 104 degrees F).*
	
   *Some trend and threshold analysis is dependent on whether the patient is awake or asleep. For example, if the blood pressure drops, the system should notice that the patient is asleep and adjust its alerts accordingly. The same is true with the respiration rate and heart rate. For example, all of these vital signs are reduced when the patient is asleep, but if awake something might be wrong.*

   *Medical professionals receive alert push notifications of a potential problem based on raw data analysis to a StayHeathy mobile app on their smart phone as well as the consolidated monitoring screen in each nurses station.*
   
   * NFRs:
     * **Configurability** - It must be easy to change vital signs thresholds for notifications. Also, the system must provide the ability to medical medical professionals and their shifts to send notifications to an appropriate person. It should’t send notifications during non-working hours of medical professionals.
     * **Performance** – MonitorMe must analyse input data without significant delays.
     
4. *If any of vital sign device (or software) fails, MonitorMe must still function for other vital sign monitoring (monitor, record, analyze, and alert).* 

   * NFRs:
     * **Fault tolerance** – If there is a fatal error in processing some of the parameter, the system must process all other parameters.


5. *Medical staff can generate holistic snapshots from a patients consolidated vital signs at any time. Medical staff can then upload the patient snapshot to MyMedicalData. The upload functionality is within the scope of the MonitorMe functionality and is done through a secure HTTP API call within MyMedicalData.*

   * NFRs:
     * **Interoperability** – The system must be able to send snapshots to MyMedicalData. 

6. *StayHealthy. Inc. will be providing a comprehensive hardware and software for this system. The platform, data stores, databases, and other technical tools and products are unspecified at this time and will be based on your on-prem architectural solution.*
   * We don’t need to pay attantion to hardware since it is already developed. 

7. *StayHealthy, Inc. is looking towards adding more vital sign monitoring devices for MonitorMe in the future.* 

   *As this is a new line of business for StayHealthy, they expect a lot of change as they learn more about this new market.* 

   * NFRs:
     * **Extensibility** – the system must be able to process new vital sign input sources in future. Additionally, it must be as easy as possible to extend the system with additional features and functionality.
 
8. *Vital sign data analyzed and recorded through MonitorMe must be as accurate as possible. After all, human lives are at stake.* 

   * NFRs:
     * **Availability** – The system must have the maximum uptime.
     * **Performance** – MonitorMe must save a lot of information for short periods of time to provide required data accuracy.

9. *StayHealthy, Inc. has always taken patient confidentially seriously. MonitorMe should be no exception to this rule. While patient monitoring data must be secure, MonitorMe does not have to meet any government regulatory requirements (e.g., HIPPA).* 
   
   * NFRs:
     * **Security** - MonitorMe must adhere to strict patient confidentiality standards, ensuring the secure handling of patient monitoring data.



### Summary 


| Given Requirements | Analysis | NFRs | 
| ------------------ | -------- | ---- |
| MonitorMe reads data from eight different patient-monitoring equipment vital sign input sources: heart rate, blood pressure, oxygen level, blood sugar, respiration rate, electrocardiogram (ECG), body temperature, and sleep status (sleep or awake). It then sends the data to a consolidated monitoring screen (per nurses station) with an average response time of 1 second or less. The consolidated monitoring screen displays each patients vital signs, rotating between patients every 5 seconds. There is a maximum of 20 patients per nurses station.| Single nurses station must be able to process data for 20 patients from 8 sources and show them to end users with max delay in 1 sec.  | Performance |
| Maximum number of patients per physical MonitorMe instance: 500.| MonitorMe phisical instance must work with 25 nurses stations. | Performance |
| MonitorMe will be deployed as an on-premises system. Each physical hospital location will have its own installation of the complete MonitorMe system (including the recorded raw monitoring data). | MonitorMe system will not be able to be installed and updated in cloud which means we must provide a possibility to easily deploy and update the system components. | Deployability |
| For each vital sign, MonitorMe must record and store the past 24 hours of all vital sign readings. A medical professional can review this history, filtering on time range as well as vital sign. | Medical personnel must be able to review the patient's history at any time to notice deterioration that has not yet reached threshold values in order to take timely action to save the patient's life. This means that the system must have maximum uptime and, in the event of a failure, no data should be lost.| Recoverability, Availability |
| In addition to recording raw monitoring data, the MonitorMe software must also analyze each patient’s vital signs and alert a medical professional if it detects an issue (e.g., decrease in oxygen level) or reaches a preset threshold (e.g., temperature has reached 104 degrees F). | The system must analyze data quickly in order to promptly detect deviations from threshold values, since the patient’s life depends on it. | Performance | 
| Some trend and threshold analysis is dependent on whether the patient is awake or asleep. For example, if the blood pressure drops, the system should notice that the patient is asleep and adjust its alerts accordingly. The same is true with the respiration rate and heart rate. For example, all of these vital signs are reduced when the patient is asleep, but if awake something might be wrong. | The system shall provide a possibility to configure different thresholds for sleep and awake modes. | Configurability |
| Medical professionals receive alert push notifications of a potential problem based on raw data analysis to a StayHeathy mobile app on their smart phone as well as the consolidated monitoring screen in each nurses station. | We need to develop a mobile app for receiving push notifications. In addition, the system must be able to sent notifications without any delays because it is critical to receive notifications on time. Also, MonitorMe shall provide a configuration for medical professionals shifts to send a notification to an appropriate person whithin his working hours. Since the push notifications could be delivered with delays due to therd-party services issues, we can consider integration with phisical alarm system inside clinics. | Performance, Configurability |
| If any of vital sign device (or software) fails, MonitorMe must still function for other vital sign monitoring (monitor, record, analyze, and alert). | The system must be stable in case of issues.| Fault tolerance | 
| Medical staff can generate holistic snapshots from a patients consolidated vital signs at any time. Medical staff can then upload the patient snapshot to MyMedicalData. The upload functionality is within the scope of the MonitorMe functionality and is done through a secure HTTP API call within MyMedicalData. | The system must be integrated with MyMedicalData.| Interoperability | 
| StayHealthy. Inc. will be providing a comprehensive hardware and software for this system. The platform, data stores, databases, and other technical tools and products are unspecified at this time and will be based on your on-prem architectural solution. | The hardware part of the system is out of scope of the project. | N/A | 
| StayHealthy, Inc. is looking towards adding more vital sign monitoring devices for MonitorMe in the future. As this is a new line of business for StayHealthy, they expect a lot of change as they learn more about this new market.| The system shall be ready for future changes.| Extensibility |
| Vital sign data analyzed and recorded through MonitorMe must be as accurate as possible. After all, human lives are at stake. | All the data must be available even after the system crash. Alaso, the system must process all input data without delays. | Availability, Performance | 
| StayHealthy, Inc. has always taken patient confidentially seriously. MonitorMe should be no exception to this rule. While patient monitoring data must be secure, MonitorMe does not have to meet any government regulatory requirements (e.g., HIPPA). | The system must encrypt sensitive personal data like patient name, birthday and so on.  | Security | 
