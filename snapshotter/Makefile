PREFIX ?= out/

all: cvmfs_snapshotter

cvmfs_snapshotter: 
        TAG=$(grep CVMFS_VERSION ../CMakeLists.txt | awk '{print $3}')
	go build -o $(PREFIX)$@ -ldflags '-X main.version=$(TAG)'

release: cvmfs_snapshotter
	mkdir -p release/usr/local/bin
	cp -r out/* release/usr/local/bin
	cp -r script/config/* release/
