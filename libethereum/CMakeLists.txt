cmake_policy(SET CMP0015 NEW)

include_directories(../../secp256k1/include)
link_directories(../../secp256k1)

aux_source_directory(. SRC_LIST)
add_library(ethereum ${SRC_LIST})

find_package(Threads REQUIRED)

target_link_libraries(ethereum secp256k1)
target_link_libraries(ethereum miniupnpc)
target_link_libraries(ethereum leveldb)
target_link_libraries(ethereum cryptopp)
target_link_libraries(ethereum gmp)
target_link_libraries(ethereum boost_system)
target_link_libraries(ethereum boost_filesystem)
target_link_libraries(ethereum ${CMAKE_THREAD_LIBS_INIT})
