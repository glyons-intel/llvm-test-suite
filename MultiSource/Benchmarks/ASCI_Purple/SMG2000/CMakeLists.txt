list(APPEND CPPFLAGS -D_POSIX_SOURCE -DHYPRE_TIMING -DHYPRE_SEQUENTIAL )
list(APPEND CPPFLAGS -I. )
list(APPEND LDFLAGS -lm)
if(SMALL_PROBLEM_SIZE)
  set(RUN_OPTIONS "-n 30 15 30 -c 0.1 1.0 10.0")
else()
  set(RUN_OPTIONS "-n 100 40 100 -c 0.1 1.0 10.0")
endif()
llvm_multisource(smg2000)
target_include_directories(smg2000 PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
