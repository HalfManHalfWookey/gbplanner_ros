cmake_minimum_required(VERSION 2.8.3)
project(planner_msgs)
find_package(catkin REQUIRED COMPONENTS
std_msgs
geometry_msgs
message_generation
actionlib_msgs)

add_service_files(
  DIRECTORY srv
  FILES
  planner_srv.srv
  planner_global.srv
  planner_teleop.srv
  planner_search.srv
  planner_homing.srv
  planner_set_homing_pos.srv
  planner_geofence.srv
  planner_request_path.srv
  pci_trigger.srv
  pci_homing_trigger.srv
  pci_set_homing_pos.srv
  pci_initialization.srv
  pci_search.srv
  pci_global.srv
  pci_stop.srv
  pci_geofence.srv
  pci_to_waypoint.srv
  planner_set_global_bound.srv
  planner_set_vel.srv
  planner_set_exp_mode.srv
  planner_string_trigger.srv
)

add_message_files(
  DIRECTORY msg
  FILES
  RobotStatus.msg
  RectangleShape.msg
  BoundMode.msg
  PlanningMode.msg
  ExecutionPathMode.msg
  TriggerMode.msg
  PlannerStatus.msg
  PlanningBound.msg
  Vertex.msg
  Edge.msg
  Graph.msg
)

generate_messages(
  DEPENDENCIES
  geometry_msgs
  actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime geometry_msgs
)
