# Run packer in a container
#
# docker run -it \
#     --rm \
#     --net host \
#     --privileged \
#     --cap-add ALL \
#     -e PACKER_LOG=1 \
#     -e PACKER_LOG_PATH="packer.log" \
#     -v /lib/modules:/lib/modules:ro \
#     -v "${PWD}:/tmp/" \
#     --workdir /tmp/  \
#     --name packer \
#     docker.io/leoh0/packer-qemu "$@"

FROM hashicorp/packer:light
LABEL maintainer "Eohyung Lee <liquidnuker@gmail.com>"

RUN apk add --no-cache \
    make \
    qemu \
    qemu-img \
    qemu-system-x86_64 \
    # Support UEFI
    ovmf
