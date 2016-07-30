cmake_minimum_required(VERSION 2.8.3)
project(needybot_srvs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  rospy
  kobuki_msgs 
  needybot_msgs 
)

add_service_files(
  DIRECTORY
    srv 
  FILES
    AbortTask.srv
    CheckHealthy.srv
    Float.srv
    Message.srv
    NextStep.srv
    NextTask.srv
    SafetyService.srv
    SimpleService.srv
    StepTask.srv
    TaskPayload.srv
    TaskStatus.srv
    Toggle.srv
    UIMessage.srv
)

generate_messages(
  DEPENDENCIES
    kobuki_msgs 
    needybot_msgs 
)

catkin_package(
  #LIBRARIES
  #  ${PROJECT_NAME}            
  CATKIN_DEPENDS
    message_runtime
    kobuki_msgs 
    needybot_msgs 
    rospy
)
