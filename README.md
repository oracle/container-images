# What's in this repository?

This repo stores the [official Oracle Linux base images](https://hub.docker.com/_/oraclelinux) in the form of tarballs containing a rootfs in two architecture-specific branches. These images are automatically consumed by the Docker Hub and are not intended for direct use by end-users.

## How to use these images

The Oracle Linux images are intended for use in the **FROM** field of a downstream `Dockerfile`. For example, to use the latest optimized Oracle Linux 7 image, specify `FROM oraclelinux:7-slim`.

## What is the difference between `oraclelinux:7` and `oraclelinux:7-slim`?

Oracle recommends using `oraclelinux:7-slim` as your base layer as it contains just enough packages for `yum` to work to install more packages. Therefore, it has the smallest size and the least amount of unneeded content.

The `oraclelinux:7` images is based off the package set what would be installed via a Minimal install of Oracle Linux.

## What is the difference between `oraclelinux:8` and `oraclelinux:8-slim`?

As with Oracle Linux 7, the `8-slim` variant contains just enough packages to install more. However, it also replaces the standard `dnf` client with the tiny `microdnf` tool to further reduce space. If you need the functionality of the full client, you can install it via `RUN microdnf -y install dnf` in your downstream `Dockerfile`.

## Where can I find images of Oracle products?

We provide sample Dockerfiles for several Oracle products in the [Oracle Docker Images](https://github.com/oracle/docker-images) repository on GitHub. Many of these images are also available for direct download from the [Oracle Container Registry](https://container-registry.oracle.com).

# What is Oracle Linux?

Oracle Linux is an open-source operating system available under the GNU General Public License (GPLv2). Suitable for general purpose or Oracle workloads, it benefits from rigorous testing of more than 128,000 hours per day with real-world workloads and includes unique innovations such as Ksplice for zero-downtime kernel patching, DTrace for real-time diagnostics, the powerful Btrfs file system, and more.

## License
Oracle Linux is released under the GPLv2. See the ```LICENSE``` file in this repository for more information.

## Support
Oracle provides support to Oracle Linux subscription customers via the [My Oracle Support](https://support.oracle.com) portal. The Oracle Linux Docker images are covered by Oracle Linux Basic and Premier support subscriptions. Customers should follow existing support procedures to obtain support for Oracle Linux running in a Docker container.

For users without an Oracle Linux support subscription, the following resources are available:

* The [Oracle Technology Network Community](https://community.oracle.com/welcome)
* The [Oracle Linux Space](https://community.oracle.com/community/server_%26_storage_systems/linux/oracle_linux) on OTN.
* The [Containers and Orchestration Space](https://community.oracle.com/community/server_&_storage_systems/linux/containers-and-orchestration) on OTN.
* The `#oracle-linux` IRC channel on Freenode.

### Official resources

* [Learn more about Oracle Linux](https://oracle.com/linux)
* [Unbreakable Linux Network](https://linux.oracle.com)
* [Oracle Linux Yum Server](https://yum.oracle.com)

### Social media resources
* [Twitter](https://twitter.com/OracleLinux)
* [Facebook](https://www.facebook.com/OracleLinux)
* [YouTube](https://www.youtube.com/user/OracleLinuxChannel)
* [Oracle Linux Blog](https://blogs.oracle.com/linux)
