# OMPL_DIR is the installation prefix for OMPL.
# YOU MUST CHANGE THIS VARIABLE depending on your installation!
# /usr for the virtual machine and deb packages
# /usr/local for install script
# /opt/local for OS X using MacPorts
OMPL_DIR=/usr/local

# Compilation flags
CXX_FLAGS=-std=c++11 -O2
# Change the -O2 flag to -g -O0 when debugging code, -O2 is for optimization.
# -g allows you to use tools like gdb to analyze your code.

# Include directories
INCLUDE_FLAGS=-I${OMPL_DIR}/include
# Linker options
LD_FLAGS=-L${OMPL_DIR}/lib -lompl -Wl,-rpath ${OMPL_DIR}/lib

# The c++ compiler to invoke
CXX=c++

all:	MyRigidBodyPlanning

clean:
	rm -f *.o
	rm -f MyRigidBodyPlanning

MyRigidBodyPlanning: MyRigidBodyPlanning.o CollisionChecking.o Transformation.o RTP.o
	$(CXX) $(CXXFLAGS) $(INCLUDE_FLAGS) -o MyRigidBodyPlanning MyRigidBodyPlanning.o CollisionChecking.o Transformation.o RTP.o $(LD_FLAGS)

%.o: %.cpp
	$(CXX) -c $(CXX_FLAGS) $(INCLUDE_FLAGS) $< -o $@
