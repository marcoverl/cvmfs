PREFIX ?= out/

all: cvmfs_snapshotter

cvmfs_snapshotter: 
	go build -o $(PREFIX)$@ -ldflags "-X main.version=${GITHUB_TAG}"

release: cvmfs_snapshotter
	mkdir -p release/usr/local/bin
	cp -r out/* release/usr/local/bin
	cp -r script/config/* release/
