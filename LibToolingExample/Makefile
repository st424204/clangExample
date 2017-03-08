LLVM_CONFIG=llvm-config

CXX=clang
CXXFLAGS=`$(LLVM_CONFIG) --cxxflags --ldflags` --std=c++11 -lstdc++
LDFLAGS=-lclangTooling -lclangFrontendTool -lclangFrontend -lclangDriver -lclangSerialization \
-lclangCodeGen -lclangParse -lclangSema -lclangStaticAnalyzerFrontend \
-lclangStaticAnalyzerCheckers -lclangStaticAnalyzerCore -lclangAnalysis \
-lclangARCMigrate -lclangRewrite -lclangRewriteFrontend -lclangEdit -lclangAST -lclangLex -lclangBasic -lclang \
`$(LLVM_CONFIG) --libs --system-libs`

all: example

example: Example.cpp
	$(CXX) $(CXXFLAGS)  Example.cpp -o example $(LDFLAGS) 

run:
	./example test.c --

clean:
	rm -f example
