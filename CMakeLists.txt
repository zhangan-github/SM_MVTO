cmake_minimum_required(VERSION 3.8)
project(TransactionalSTOScheduler)

set(CMAKE_CXX_STANDARD 11)
set(TBB_DIR "/home/zhangan/ExternalLib/tbb2018_20170919oss")
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -g -pthread")

set(SOURCE_FILES main.cpp src/Transaction/lock/RWLock.cpp src/Transaction/lock/RWLock.h src/Transaction/lock/LockKey.cpp src/Transaction/lock/LockKey.h src/Util/Log.h src/Transaction/TXAbortException.cpp src/Transaction/TXAbortException.h src/Transaction/Transaction.cpp src/Transaction/Transaction.h src/Boosting/BaseContainer.cpp src/Boosting/BaseContainer.h src/Boosting/Boosted_map.cpp src/Boosting/Boosted_map.h src/Util/ThreadUtil.h src/Transaction/lock/Abstract.h src/Testing/TestTransaction.h src/Transaction/lock/Abstract.cpp src/Util/Log.cpp src/Testing/TestTransaction.cpp src/Testing/testBoostedMap.hpp src/Scheduler/MultiVersion/MVSTOScheduler.cpp src/Scheduler/MultiVersion/MVSTOScheduler.h src/Scheduler/MultiVersion/WSetTransaction.cpp src/Scheduler/MultiVersion/WSetTransaction.h src/Scheduler/MultiVersion/MVBaseContainer.cpp src/Scheduler/MultiVersion/MVBaseContainer.h src/Util/ContainerInstantiate.h src/Util/ContainerInstantiate.cpp src/Testing/testMVScheduler.h src/Testing/testMVScheduler.cpp)
add_executable(TransactionalSTOScheduler ${SOURCE_FILES})

find_package(Threads REQUIRED)
find_package(TBB REQUIRED)

target_link_libraries(TransactionalSTOScheduler Threads::Threads)
target_link_libraries(TransactionalSTOScheduler tbb)
