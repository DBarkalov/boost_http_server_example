Сборка http сервера
https://www.boost.org/doc/libs/develop/libs/beast/example/http/server/fast/http_server_fast.cpp
https://www.boost.org/doc/libs/develop/libs/beast/doc/html/beast/examples.html#beast.examples.servers

1 install boost library

	wget https://dl.bintray.com/boostorg/release/1.68.0/source/boost_1_68_0.tar.gz

	./bootstrap.sh --prefix=/usr/
	./b2
	sudo ./b2 install

2 compile http server

	cmake --build ./

3 запуск http сервера

	./httpserver 0.0.0.0 8089 . 100 spin


Тест производительности
	sudo apt-get install apache2-utils

	ab -c 10 -n 100 http://127.0.0.1:8089/fields_alloc.hpp

Результат

Document Path:          /fields_alloc.hpp
Document Length:        4115 bytes

Concurrency Level:      10
Time taken for tests:   0.153 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      4222000 bytes
HTML transferred:       4115000 bytes
Requests per second:    6532.36 [#/sec] (mean)
Time per request:       1.531 [ms] (mean)
Time per request:       0.153 [ms] (mean, across all concurrent requests)
Transfer rate:          26933.23 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:     1    1   0.7      1       5
Waiting:        0    1   0.4      1       4
Total:          1    2   0.8      1       5

