BootStrap: docker
From: python:3.6.8-slim

%files
    ./requirements.txt /tmp/

%post
    BUILDPKGS="build-essential apt-utils" && \
    apt-get update && \
    apt-get install -y $BUILDPKGS && \
    apt-get install -y procps

    pip install --no-cache-dir -r /tmp/requirements.txt
    pip install --no-cache-dir --upgrade pyscenic==0.9.11
    pip install --no-cache-dir --upgrade ipykernel

    apt-get remove --purge -y $BUILDPKGS && \
    rm -rf /var/lib/apt/lists/*

