set(BENCHMARK_ENABLE_TESTING NO)

FetchContent_Declare(
        benchmark
        GIT_REPOSITORY https://github.com/google/benchmark.git
        GIT_TAG main
)

FetchContent_MakeAvailable(benchmark)

add_executable(benchmark_run ./benchmark.cpp ../include/mystring.h ../src/mystring.cpp)

target_link_libraries(benchmark_run benchmark::benchmark)

target_include_directories(benchmark_run PUBLIC ../include)
