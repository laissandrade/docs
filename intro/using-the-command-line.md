# Using the CLI

###### The *WeDeploy™ Command-line interface (CLI)* is a tool that wraps the WeDeploy Platform API, providing support for things like creating, managing and scaling applications. It's generally installed in your local development operating system.

<!-- <article id="1-dependencies"> -->

## Dependencies

The following external software dependencies are necessary to correctly run some commands:

**A) Docker**

Docker is a tool that automates the deployment of WeDeploy containers in your local environment.

  * [Mac OS X](https://download.docker.com/mac/stable/Docker.dmg)
  * [Windows](https://download.docker.com/win/stable/InstallDocker.msi)
  * [Linux](https://docs.docker.com/engine/installation/linux/)


**B) Git**

Git is a version control system that is required for working with WeDeploy projects.

* [Mac OS X](https://git-scm.com/download/mac)
* [Windows](https://git-scm.com/download/win)
* [Linux](https://git-scm.com/download/linux)

The availability of dependencies are tested just before its immediate use. If a required dependency is not found, an useful error message is printed and the calling process is terminated with an error code.

<!-- </article> -->


<!-- <article id="2-installing"> -->

## Installing

Install this tool with:

```
curl http://cdn.wedeploy.com/cli/latest/wedeploy.sh -s | bash
```

To update this tool, just run `we update`.

<!-- </article> -->


<!-- <article id="3-creating-projects"> -->

## Creating projects locally from the CLI

The project is the fundamental unit of organization on *WeDeploy™*. Each project can be associated with its own set of provisioned services.

Use `we create` to create projects and containers. You can create a project anywhere on your machine. Containers can only be created from inside projects and are stored on the first subdirectory of its project.

```
Usage:
  we create <project/container id> [flags]
```

Examples:

`we create appexample`

```
Global Flags:
      --no-color        Disable color output
      --remote string   Remote to use
  -v, --verbose         Verbose output
```
<!-- </article> -->

<!-- <article id="4-running-projects-locally"> -->

## Running projects locally from the CLI

1. Start local infrastructure:

  ```sh
we run
  ```

2. Clone this repository:

  ```sh
git clone https://github.com/wedeploy/boilerplate-hosting.git
cd boilerplate-hosting
  ```

3. Link this container with the local infrastructure:

  ```sh
we link
  ```

4. Now your container is ready to be used:

  ```
http://hosting.<projectID>.wedeploy.me
  ```

<!-- </article> -->

## Fetch project logs

To fetch your logs, use the `we logs` command.

Usage:

```
we logs [project] [container] --instance hash [flags]
```

Examples:

```
we logs (on project or container directory)
we logs chat
we logs portal email
we logs portal email --instance abc
```

Flags:

```
      --instance string   Instance ID or hash
      --level string      Severity (critical, error, warning, info (default), debug)
      --since string      Show since moment (i.e., 20min, 3h, UNIX timestamp)
  -w, --watch             Watch / follow log output
```

Global Flags:

```
      --no-color        Disable color output
      --remote string   Remote to use
  -v, --verbose         Verbose output
```