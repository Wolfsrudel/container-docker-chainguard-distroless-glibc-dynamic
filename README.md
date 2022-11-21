# glibc-dynamic

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/chainguard-images/readme-generator
-->

[![CI status](https://github.com/chainguard-images/glibc-dynamic/actions/workflows/release.yaml/badge.svg)](https://github.com/chainguard-images/glibc-dynamic/actions/workflows/release.yaml)

Base image with just enough to run arbitrary glibc binaries.<br/><br/>This image is meant to be used as just a base image only. It does not contain any programs that can be run, other than `/sbin/ldconfig`.<br/><br/>You must bring your own artifacts to use this image, e.g. with a Docker multi-stage build. If you want locale support other than `C.UTF-8`, you must bring your own locale data as well. This may change in the future based on user feedback.<br/><br/>See also [musl-dynamic](https://github.com/chainguard-images/musl-dynamic) which is an equivalent image for running dynamically-linked musl binaries.

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/glibc-dynamic:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `migration-20221118` | `sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa) | `amd64` |
| `migration` `migration-20221121` | `sha256:0429667c854c3d9af153c29d7478435b0c8ebef2537a42de59558bc0c5f42862`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:0429667c854c3d9af153c29d7478435b0c8ebef2537a42de59558bc0c5f42862) | `amd64` |
| `migration-20221119` | `sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6) | `amd64` |
| `migration-20221120` | `sha256:df46c5684211201b44996a42fe8a2782ebcb5a00165c7909ca46048b8cdd3a21`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:df46c5684211201b44996a42fe8a2782ebcb5a00165c7909ca46048b8cdd3a21) | `amd64` |
| `latest` | `sha256:bd8ffbc8eb0ff59eca13d40bdb59c40c855bfd4229d23d127e987632b08ca8fa`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:bd8ffbc8eb0ff59eca13d40bdb59c40c855bfd4229d23d127e987632b08ca8fa) | `amd64` |



## Signing

All Chainguard Images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify cgr.dev/chainguard/glibc-dynamic:latest | jq
```

Output:
```
Verification for cgr.dev/chainguard/glibc-dynamic:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/chainguard-images/glibc-dynamic"
      },
      "image": {
        "docker-manifest-digest": "sha256:bd8ffbc8eb0ff59eca13d40bdb59c40c855bfd4229d23d127e987632b08ca8fa"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "70c1ff291a6437a6c8cdebac8011a2ddaf452f90",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/glibc-dynamic",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCIEZs8b1q7Rz4X20C7vf2ABC2TcRTcIRGQbhEKzM9hv9xAiBTiz+WygccLitbLmVthiLO+JaX+o08n0IC7VvoCViVUA==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiJhYTJhMDMzODI3Y2JmNDE2NWE0MzBmZDI1YWMwMGFhYTc4MjAyMzNhNDNkZTk1MjhiNTI2ZTZhNGYxNTU2MjZkIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJQTBpYjREL1doRUdBQjZabnhQN1JYNXJlMG9Bb1doRzBQSENUc0ExNEFjRkFpRUE3djVHMDlQSVZ3ekVKZ3ZYM2kyYUJwMktxbG5yd1QxTVQ5VC9aUnFnN0xFPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUjFWRU5EUVhvMlowRjNTVUpCWjBsVlEzaFlObmhrVW5acGVVUlJNMFp2YUd3MFFuZEdSVFF3Umt4UmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVU1hoTlJFbDNUbFJGZDFkb1kwNU5ha2w0VFZSSmVFMUVTWGhPVkVWM1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZTVFUxQmVVaDFVU3RoVGprNE5GRTBibXMxWTNGc1dEWTRVRGxWYTNsdlJqVXZiR1FLY21Fd2JFVXZSa1V6T1VKTFkwdE9OekprTWsxeVZEVkllVFp4TmpsbmJFZFVabFZMYW1KclRYZENNMnhvUjJwTU9VdFBRMEZzTUhkblowcGFUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlU0YVVFekNqZDNPR2hGYVU1S1dVcDVaMDVTWjA4NWFXMUpNa2xWZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDJKM1dVUldVakJTUVZGSUwwSkhWWGRaTkZwb1lVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5WkhOaFYwcHFURmRTTldKdFJuUmhWMDEyVEcxa2NHUkhhREZaYVRrellqTktjbHB0ZUhaa00wMTJZMjFXYzFwWFJucGFVelUxQ2xsWE1YTlJTRXBzV201TmRtRkhWbWhhU0UxMllsZEdjR0pxUVRWQ1oyOXlRbWRGUlVGWlR5OU5RVVZDUWtOMGIyUklVbmRqZW05MlRETlNkbUV5Vm5VS1RHMUdhbVJIYkhaaWJrMTFXakpzTUdGSVZtbGtXRTVzWTIxT2RtSnVVbXhpYmxGMVdUSTVkRTFDV1VkRGFYTkhRVkZSUW1jM09IZEJVVWxGUTBoT2FncGhSMVpyWkZkNGJFMUVXVWREYVhOSFFWRlJRbWMzT0hkQlVVMUZTMFJqZDFsNlJtMWFha2sxVFZkRk1rNUVUVE5aVkZwcVQwZE9hMXBYU21oWmVtZDNDazFVUm1oTmJWSnJXVmRaTUU1VVNtMVBWRUYzU0VGWlMwdDNXVUpDUVVkRWRucEJRa0pCVVU5Uk0wcHNXVmhTYkVsR1NteGlSMVpvWXpKVmQweFJXVXNLUzNkWlFrSkJSMFIyZWtGQ1FsRlJabGt5YUdoaFZ6VnVaRmRHZVZwRE1YQmlWMFp1V2xoTmRsb3llSEJaYlUxMFdraHNkVmxYTVhCWmVrRmtRbWR2Y2dwQ1owVkZRVmxQTDAxQlJVZENRVGw1V2xkYWVrd3lhR3haVjFKNlRESXhhR0ZYTkhkbldXdEhRMmx6UjBGUlVVSXhibXREUWtGSlJXVjNValZCU0dOQkNtUlJSR1JRVkVKeGVITmpVazF0VFZwSWFIbGFXbnBqUTI5cmNHVjFUalE0Y21ZclNHbHVTMEZNZVc1MWFtZEJRVUZaVTFnM2NXRm5RVUZCUlVGM1FrY0tUVVZSUTBsSFJ6TjNUakUwTWtKS2NUYzRhVFo0VEZweWJVSXdaVEJzYjFnMVFVOWhka3czV2psQmEyeHVLMGR1UVdsQ1FsUjZUa1JIWVdoamRHSjBXQXBJYVRNeFdVOHpiM05yY0VSc2IzWnpORm95WkdzeU5FcHhiWFZtTDJwQlMwSm5aM0ZvYTJwUFVGRlJSRUYzVG5CQlJFSnRRV3BGUVhoM1VXdFhLMm96Q21KVGNEWndSemczU1ZFMWRFTlhUV3BqZGt0UWRua3dZMkZXYTJwWlRuWnRjV1JSZW1jcmFsWkpiMWhTVWpOa1dFVmFjR2xRWnpVMFFXcEZRVEJhUjFjS1QwZGxhV2xOYVcxeVprcFlUVEJ3VlZScVQzTnVka0ZQVmpGMGRsZG5MMGgxTURZeWQwNXRiMDQ1U1hkMWNUVmtkMXB3VXpkSFZrWjRPWGRLQ2kwdExTMHRSVTVFSUVORlVsUkpSa2xEUVZSRkxTMHRMUzBLIn19fX0=",
          "integratedTime": 1668996316,
          "logIndex": 7510938,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/glibc-dynamic/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/glibc-dynamic",
      "githubWorkflowSha": "70c1ff291a6437a6c8cdebac8011a2ddaf452f90",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3510854594",
      "sha": "70c1ff291a6437a6c8cdebac8011a2ddaf452f90"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

