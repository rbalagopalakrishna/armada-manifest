Armada Quick Start (via Container)

launch the Armada container by executing:

$ sudo docker run -d --net host -p 8000:8000 --name armada \
    -v ~/.kube/config:/armada/.kube/config \
    -v $(pwd)/examples/:/examples quay.io/airshipit/armada:latest-ubuntu_bionic

$ clone https://github.com/rbalagopalakrishna/armada-manifest.git

$ cd ~/armada-manifest

Copy armada manifest to Docker Container
$ sudo docker cp armada-manifest.yaml armada:/armada/armada-manifest.yaml

Run
$ sudo docker exec armada armada apply /armada/armada-manifest.yaml
