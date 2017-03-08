LLVM_CONFIG=llvm-config

CXX=`$(LLVM_CONFIG) --bindir`/clang
CXXFLAGS=`$(LLVM_CONFIG) --cppflags` -fPIC -fno-rtti --std=c++14
LDFLAGS=`$(LLVM_CONFIG) --ldflags` -shared

all: hello.so

hello.so: Hello.o
	$(CXX) -shared Hello.o -o hello.so $(LDFLAGS) 

Hello.o: Hello.cpp
	$(CXX) -c Hello.cpp -o Hello.o $(CXXFLAGS)

run:
	opt -load ./hello.so -hello hello.bc >> /dev/null

clean:
	rm -f *.o hello.so
