FROM alpine:latest

RUN apk add cmake make gcc g++ git
# Installing google test
RUN git clone https://github.com/google/benchmark.git
RUN cmake -E make_directory "benchmark/build"
RUN cmake -E chdir "benchmark/build" cmake -DBENCHMARK_DOWNLOAD_DEPENDENCIES=on -DBENCHMARK_ENABLE_GTEST_TESTS=OFF -DCMAKE_BUILD_TYPE=Release ../
RUN cmake --build "benchmark/build" --config Release
RUN cmake --build "benchmark/build" --config Release --target install

CMD ["/bin/sh"]


