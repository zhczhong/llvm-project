add_header_library(
  threads_utils
  HDRS
    Futex.h
  DEPENDS
    libc.include.sys_syscall
    libc.include.threads
    libc.src.__support.CPP.atomic
    libc.src.__support.CPP.mutex
    libc.src.__support.OSUtil.osutil
    libc.src.__support.threads.mutex
    libc.src.__support.threads.linux.raw_mutex
    libc.src.__support.threads.linux.futex_utils
)

add_entrypoint_object(
  cnd_init
  SRCS
    cnd_init.cpp
  HDRS
    ../cnd_init.h
  DEPENDS
    libc.include.threads
    libc.src.__support.threads.CndVar
)

add_entrypoint_object(
  cnd_destroy
  SRCS
    cnd_destroy.cpp
  HDRS
    ../cnd_destroy.h
  DEPENDS
    libc.include.threads
    libc.src.__support.threads.CndVar
)

add_entrypoint_object(
  cnd_wait
  SRCS
    cnd_wait.cpp
  HDRS
    ../cnd_wait.h
  DEPENDS
    libc.include.threads
    libc.src.__support.threads.mutex
    libc.src.__support.threads.CndVar
)

add_entrypoint_object(
  cnd_signal
  SRCS
    cnd_signal.cpp
  HDRS
    ../cnd_signal.h
  DEPENDS
    libc.include.threads
    libc.src.__support.threads.CndVar
)

add_entrypoint_object(
  cnd_broadcast
  SRCS
    cnd_broadcast.cpp
  HDRS
    ../cnd_broadcast.h
  DEPENDS
    libc.include.threads
    libc.src.__support.threads.CndVar
)
