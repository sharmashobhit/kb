Docker buld kit is used to build the image for cross platform implementation.

## How to setup the build environment

```bash
docker buildx create --use desktop-linux --config buildkitd.toml
```

Here `buildkitd.toml` is used to specify the configuration of the build environment. In my particular case, I have a self hosted docker image registry for my Kubernetes cluster. You can set up insecure registry url in the buildkit like this:

```toml
[registry."<host>:<port>"]
http = true
```


[Reference](https://docs.docker.com/build/buildkit/toml-configuration/)