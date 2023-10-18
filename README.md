# Oracle Linux base images

This repo stores the architecture-specific rootfs tarballs for the official
Oracle Linux base images published on [Docker Hub](https://hub.docker.com/_/oraclelinux)
and [GitHub Container Registry](https://github.com/orgs/oracle/packages/container/package/oraclelinux).

## Oracle Linux

Oracle Linux is an open-source operating system available under the GNU General
Public License (GPLv2). Suitable for general purpose or Oracle workloads,
it benefits from rigorous testing of more than 128,000 hours per day with
real-world workloads and includes unique innovations such as Ksplice for
zero-downtime kernel patching, DTrace for real-time diagnostics, the powerful
Btrfs file system, and more.

## How to use these images

The Oracle Linux images are intended for use in the **FROM** field of a
downstream `Dockerfile`. For example, to use the latest optimized Oracle Linux
7 image, specify `FROM oraclelinux:7-slim`.

## Changelog

Due to the fact that only the latest tarball for each tag is stored in the
`dist-amd64` and `dist-arm64v8` branches, it is not possible to use Git's
history to determine what has changed and when. Thus, we maintain a
[CHANGELOG](https://github.com/oracle/container-images/blob/master/CHANGELOG.md)
in the `master` branch that documents the changes made to various images by date.

## Differences between `oraclelinux:7` and `oraclelinux:7-slim`

Oracle recommends using `oraclelinux:7-slim` as your base layer as it contains
just enough packages for `yum` to work to install more packages. Therefore, it
has the smallest size and the least amount of unneeded content.

The `oraclelinux:7` images is based off the package set what would be installed
via a Minimal install of Oracle Linux.

## Differences between `oraclelinux:8` and `oraclelinux:8-slim`

As with Oracle Linux 7, the `8-slim` variant contains just enough packages to
install more.

However, it also replaces the standard `dnf` client with the tiny
`microdnf` tool to further reduce space. If you need the functionality of the
full client, you can install it via `RUN microdnf install dnf` in your
downstream `Dockerfile`.

To provide `yum` compatibility, use `RUN microdnf install yum`.

### Using modules with `microdnf`

An example of how to enable module support when using `microdnf` can be seen
in the [`oraclelinux:8`](https://github.com/oracle/docker-images/tree/master/OracleLinuxDevelopers/oraclelinux8)
variants of the [`OracleLinuxDeveloper`](https://github.com/oracle/docker-images/tree/master/OracleLinuxDevelopers)
images in the [Oracle Docker Images repo](https://github.com/oracle/docker-images).

## Finding container images of Oracle products

We provide sample Dockerfiles for several Oracle products in the
[Oracle Docker Images](https://github.com/oracle/docker-images) repository on
GitHub. Many of these images are also available for direct download from
the [Oracle Container Registry](https://container-registry.oracle.com).

## Contributing

This project is not accepting external contributions at this time. For bugs or enhancement requests, please file a GitHub issue unless it’s security related. When filing a bug remember that the better written the bug is, the more likely it is to be fixed. If you think you’ve found a security vulnerability, do not raise a GitHub issue and follow the instructions in our [security policy](./SECURITY.md).

## Security

Please consult the [security guide](./SECURITY.md) for our responsible security vulnerability disclosure process

## License

Oracle Linux is released under the GPLv2. See the ```LICENSE``` file in this
repository for more information.

## Support

Oracle provides support to Oracle Linux subscription customers via the
[My Oracle Support](https://support.oracle.com) portal. The Oracle Linux Docker
images are covered by Oracle Linux Basic and Premier support subscriptions.
Customers should follow existing support procedures to obtain support for Oracle
Linux running in a Docker container.

For users without an Oracle Linux support subscription, the following resources
are available:

* The [Oracle Technology Network Community](https://community.oracle.com/welcome)
* The [Oracle Applications and Infrastructure Community](https://community.oracle.com/tech/apps-infra/categories/oracle_linux).

### Official resources

* [Learn more about Oracle Linux](https://oracle.com/linux)
* [Unbreakable Linux Network](https://linux.oracle.com)
* [Oracle Linux Yum Server](https://yum.oracle.com)

### Social media resources

* [Twitter](https://twitter.com/OracleLinux)
* [Facebook](https://www.facebook.com/OracleLinux)
* [YouTube](https://www.youtube.com/user/OracleLinuxChannel)
* [Oracle Linux Blog](https://blogs.oracle.com/linux)
