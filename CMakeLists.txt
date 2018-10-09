cmake_minimum_required(VERSION 2.8.3)
project(iai_image_logging_msgs)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED
        dynamic_reconfigure
        message_generation
        std_msgs
        sensor_msgs)

generate_dynamic_reconfigure_options(
        cfg/Main.cfg
        cfg/Compressed.cfg
        cfg/Theora.cfg
)

add_service_files(
        DIRECTORY
        srv
        FILES
        Log.srv
        Update.srv
        Configuration.srv
        ConfigurationYAML.srv
)

generate_messages(
    DEPENDENCIES
    std_msgs
    sensor_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime
)

include_directories(
 ${catkin_INCLUDE_DIRS}
)
