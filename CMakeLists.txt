cmake_minimum_required(VERSION 2.8.12)
project(AI4G)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

set(SRC src)

include_directories(include)

add_library(aicore STATIC
  ${SRC}/action.cpp
  ${SRC}/aimath.cpp
  ${SRC}/basesm.cpp
  ${SRC}/core.cpp
  ${SRC}/dectree.cpp
  ${SRC}/kinematic.cpp
  ${SRC}/learning.cpp
  ${SRC}/location.cpp
  ${SRC}/markovsm.cpp
  ${SRC}/qlearning.cpp
  ${SRC}/rules.cpp
  ${SRC}/sm.cpp
  ${SRC}/steering.cpp
  ${SRC}/steerpipe.cpp
  ${SRC}/timing.cpp
  ${SRC}/demos/common/gl/app.cpp
  ${SRC}/demos/common/gl/main.cpp
)

set(DEMO_DEPS aicore ${CONAN_LIBS})

add_executable(c03_flocking ${SRC}/demos/c03_flocking/flocking_demo.cpp ${SRC}/demos/c03_flocking/flock_steer.cpp)
add_executable(c03_kinematic ${SRC}/demos/c03_kinematic/kinematic_demo.cpp)
add_executable(c03_pipeline ${SRC}/demos/c03_pipeline/pipeline_demo.cpp)
add_executable(c03_priority ${SRC}/demos/c03_priority/priority_demo.cpp)
add_executable(c03_steering ${SRC}/demos/c03_steering/steering_demo.cpp)
add_executable(c05_action ${SRC}/demos/c05_action/action_demo.cpp)
add_executable(c05_dectree ${SRC}/demos/c05_dectree/dectree_demo.cpp)
add_executable(c05_hsm ${SRC}/demos/c05_hsm/hsm_demo.cpp)
add_executable(c05_markovsm ${SRC}/demos/c05_markovsm/markovsm_demo.cpp)
add_executable(c05_randectree ${SRC}/demos/c05_randectree/randectree_demo.cpp)
add_executable(c05_sm ${SRC}/demos/c05_sm/sm_demo.cpp)
add_executable(c07_simpleq ${SRC}/demos/c07_simpleq/simpleq_demo.cpp)

target_link_libraries(c03_flocking ${DEMO_DEPS})
target_link_libraries(c03_kinematic ${DEMO_DEPS})
target_link_libraries(c03_pipeline ${DEMO_DEPS})
target_link_libraries(c03_priority ${DEMO_DEPS})
target_link_libraries(c03_steering ${DEMO_DEPS})
target_link_libraries(c05_action ${DEMO_DEPS})
target_link_libraries(c05_dectree ${DEMO_DEPS})
target_link_libraries(c05_hsm ${DEMO_DEPS})
target_link_libraries(c05_markovsm ${DEMO_DEPS})
target_link_libraries(c05_randectree ${DEMO_DEPS})
target_link_libraries(c05_sm ${DEMO_DEPS})
target_link_libraries(c07_simpleq ${DEMO_DEPS})
