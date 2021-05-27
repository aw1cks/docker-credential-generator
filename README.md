# docker-credential-generator

Generate a docker-compatible `config.json` containing credentials for your registry.

### Why?

When using BuildKit in GitLab CI, you may need to log in to your registry in order to push into it.

However, `buildctl` does not provide any method to provide credentials on the command line.

Thus, in order to use the GitLab CI provided variables, you can use this program to generate the relevant `$HOME/.docker/config.json` file.

### Example usage

From your GitLab CI pipeline:

```shell
./docker-credential-generator \
  --registry $CI_REGISTRY \
  --user $CI_REGISTRY_USER \
  --password $CI_REGISTRY_PASSWORD
```

### Requirements

 - `python3`
