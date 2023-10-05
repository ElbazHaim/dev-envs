format:
	clang-format -i *.cpp

compile:
	clang++ -std=c++20 Main.cpp -o Main

execute:
	./Main

leaks:
	export MallockStackLogging=1; \
	leaks --atExit --list -- ./Main > memory_leak.log; \
	export MallockStackLogging=0; \

delete:
	rm Main

run:
	make format compile execute delete

all:
	make format run leaks delete
