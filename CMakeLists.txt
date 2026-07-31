cmake_minimum_required(VERSION 3.25...4.4)

project(tlsf C)

add_library(tlsf)

target_sources(tlsf PRIVATE tlsf.c
 PUBLIC FILE_SET HEADERS BASE_DIRS . FILES tlsf.h
)

add_library(tlsf::tlsf ALIAS tlsf)

install(TARGETS tlsf EXPORT tlsf-target FILE_SET HEADERS DESTINATION include/tlsf)
install(EXPORT tlsf-target DESTINATION lib/cmake/tlsf NAMESPACE tlsf:: FILE tlsfConfig.cmake) 
