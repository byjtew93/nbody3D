all: nbody.g


nbody.g: nbody.c
	gcc -march=native -mavx2 -Ofast -fopt-info-all=nbody.gcc.optrpt $< -o $@ -lm -fopenmp

nbody.i: nbody.c
	icc -xhost -Ofast -qopt-report $< -o $@ -qmkl -qopenmp

run_nbody.g: nbody.g
	taskset -c 3 ./nbody.g

clean:
	rm -Rf *~ *.g *.i *.optrpt

