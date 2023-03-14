# Rollic Games Data Engineer Case Study

Rollic Data Engineer Role - Case Study 2022
There are 3 types of data given in csv format: Installs, Sessions, Events.

Session data contains the session records of users' playtime. The data consist of 6 fields: USER_ID, PLATFORM, APP_NAME, CREATE_TS, INSTALL_TS, SESSION_ID

USER_ID: Unique identifier for each users
PLATFORM: Platform info (ios/android)
APP_NAME: The name of the game the user plays
CREATE_TS: Created timestamp for the session
INSTALLS_TS: Installed timestamp for the users
SESSION_ID: Unique identifier for each session records
Installs data has a record for each installs. The data consist of 5 fields: USER_ID, PLATFORM, APP_NAME, INSTALL_TS, SESSION_ID.

USER_ID: Unique identifier for each users
PLATFORM: Platform info (ios/android)
APP_NAME: The name of the game the user plays
INSTALLS_TS: Installed timestamp for the users
SESSION_ID: Session_ID of the first sessions
Events data consist of action logs of the users. The data consist of 6 fields: USER_ID, PLATFORM, APP_NAME, CREATE_TS, INSTALL_TS, EVENT_NAME, SESSION_ID

USER_ID: Unique identifier for each users
PLATFORM: Platform info (ios/android)
APP_NAME: The name of the game the user plays
CREATE_TS: Created timestamp for the event (action)
INSTALLS_TS: Installed timestamp for the users
SESSION_ID: Session_ID of the first sessions
For this case study, we have raw data files in csv format as explained above. You are expected to complete neccassary data cleaning (Data cleaning must be completed according to the explanations above.) and create aggregations for the business needs. They are explained below;

DAU: For the first task you need to find daily active users (unique users amount installed or played for each day). Results data should consist of these fields; app_name, create_date, user_count. You are expected to the use sessions data. Results must be exported in the following partitions: app_name, platform.

Retention: Here, you need to find the user retention rate. Write the code of how many users returned to the game on which day after their installation date for this game. Results data should consist of these fields; app_name, install_date, returned_user_count, day (create date - install date). You are expected to the use installs and sessions data. Results must be exported in the following partitions: retention, app_name, platform.

Level Completion Time: Level completion time can be calculated as duration between level_started and level_completed event's create timestamp in seconds. This is needed to be calculated for each users for the same session. After that, values must be averaged. Results data should consist of these fields; app_name, level, average_completion_time You are expected to the use events data. Results must be exported in the following partitions results, level, app_name, platfom.

Sessions Data: For the last task we need to improve sessions data. We will check that if the session is user's first session or not. We can check 'app_started' events data and pull that value in a boolean data type. Also, install_ts column is needed to be dropped. Results data should consist of these fields user_id, platform, app_name, create_ts, session_id, is_first_session. Events data must be used. Results must be exported in the following partition. create_date. Results have to be idempotent in terms of create date (Data shouldn't be changed if the notebook run again)

Answers are needed to be given in this notebook. Pyspark must be used for data operations (Ex: Pandas is not allowed.). Results folder and the notebook are expected to be sent in one zip file.

**Dealine is 5 days. Good Luck!**
