# scratch-cacerts

Docker image containing nothing but CA certificates. Rebuilt daily to
ensure that the latest CA certificates are always available.

Includes [attestations](https://github.com/jaredallard/scratch-cacerts/attestations)
for verification of the image's source.

## How do I verify the Docker image?

You can use the [Github CLI] to easily verify that it was created
through a Github action at a given commit. For example, to verify the
latest built image:

```bash
docker pull ghcr.io/jaredallard/scratch-cacerts
# --deny-self-hosted-runners is optional, but proves that I didn't run
# my own runners to create this image and somehow 'taint' the process.
gh attestation verify oci://ghcr.io/jaredallard/scratch-cacerts \
  --owner jaredallard --deny-self-hosted-runners
```

## License

MIT

[Github CLI]: https://cli.github.com/