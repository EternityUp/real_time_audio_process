cmake_minimum_required(VERSION 2.6)
project(real_time_audio_process)

INCLUDE_DIRECTORIES(/home/xzc/eigen3.3.4)

add_compile_options(-std=c++11)

LINK_DIRECTORIES(${CMAKE_SOURCE_DIR}/libs/)

add_executable(real_time_audio_process mic_array_processing.cpp audio_record_process_thread.cpp alsa_audio_record.cpp main.cpp)

target_link_libraries(real_time_audio_process asound pthread ArrayShapeAnalysis FourierTransform AudioFileProcess WavFileRW BasicSignalProcess)

install(TARGETS real_time_audio_process RUNTIME DESTINATION bin)
