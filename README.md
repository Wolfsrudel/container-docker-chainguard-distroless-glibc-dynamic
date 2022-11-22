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
| `latest` | `sha256:00baae9a38413a0a7783c59bd2b778eb2545b1f3d7ec97824e48c3b6def1807f`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:00baae9a38413a0a7783c59bd2b778eb2545b1f3d7ec97824e48c3b6def1807f) | `amd64` |
| `migration-20221118` | `sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa) | `amd64` |
| `migration` `migration-20221122` | `sha256:10d44bae0b06d907acd36d4e18536c10b983e9a0a01031f20156e61dc023189e`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:10d44bae0b06d907acd36d4e18536c10b983e9a0a01031f20156e61dc023189e) | `amd64` |
| `migration-20221119` | `sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6) | `amd64` |
| `migration-20221120` | `sha256:df46c5684211201b44996a42fe8a2782ebcb5a00165c7909ca46048b8cdd3a21`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:df46c5684211201b44996a42fe8a2782ebcb5a00165c7909ca46048b8cdd3a21) | `amd64` |
| `migration-20221121` | `sha256:f441a9228beedbbdd562081ca0a64041254b2339b40e5b4b7b7c9c16d3808363`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:f441a9228beedbbdd562081ca0a64041254b2339b40e5b4b7b7c9c16d3808363) | `amd64` |



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
        "docker-manifest-digest": "sha256:00baae9a38413a0a7783c59bd2b778eb2545b1f3d7ec97824e48c3b6def1807f"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "7a5d1797803856f68cabebbccd9151fc1bdf7d1b",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/glibc-dynamic",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCID1y/IPh9h2sOJeKSECwWYyKvNtlv/p0POf8YU8u+h48AiBfSC9CQxFB7zE2BKpuEMcT5CXuf0T4sO4tPcHPGEgdSQ==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIzOWY5ZWMwZWIzY2Q3NDcwZDAzZmNiMTkxMjQyOTBiYjQ3MzA2YzI0MmU0YmY1NzE0ZjQyYjI3ZDBkZjc5MjRmIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FWUNJUUQ4UFVtaWJicUNJNE9sWDA2RnBLQkFMVDI0UUozdUkwK3Q0OGd0NkREZzN3SWhBT0tUQmVkeDNIaGVXM0oxWWdrcERoTmVSS2NmQzNRSEZYZUxQNm4yZmtNWCIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUjFha05EUVhvclowRjNTVUpCWjBsVlJYWnVLMGcwYWpFelVub3dhMVpzVjAxRlRFTlFVRE5rY2tobmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVU1hsTlJFRjVUbXBWTkZkb1kwNU5ha2w0VFZSSmVVMUVRWHBPYWxVMFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZDY0VGVFdsQXpSMHB2YWxCS2N6SlRNRTVsYTJGV1IwRmhObTh6YWtJclprSnpWMFlLVTFCYU5pOTNTRXRwVG1ONGJVOVZaVU5HTWxOYVl6bEtLemhxTVhndlQzSmtZbko1YUVsdE9EUTFUa2RPUmxkSGMzRlBRMEZzTkhkblowcGhUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZzTm5Cc0NrZHZSbkJ1U2trME5uWnlVekJzUVdwb01uSjZha013ZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDJKM1dVUldVakJTUVZGSUwwSkhWWGRaTkZwb1lVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5WkhOaFYwcHFURmRTTldKdFJuUmhWMDEyVEcxa2NHUkhhREZaYVRrellqTktjbHB0ZUhaa00wMTJZMjFXYzFwWFJucGFVelUxQ2xsWE1YTlJTRXBzV201TmRtRkhWbWhhU0UxMllsZEdjR0pxUVRWQ1oyOXlRbWRGUlVGWlR5OU5RVVZDUWtOMGIyUklVbmRqZW05MlRETlNkbUV5Vm5VS1RHMUdhbVJIYkhaaWJrMTFXakpzTUdGSVZtbGtXRTVzWTIxT2RtSnVVbXhpYmxGMVdUSTVkRTFDV1VkRGFYTkhRVkZSUW1jM09IZEJVVWxGUTBoT2FncGhSMVpyWkZkNGJFMUVXVWREYVhOSFFWRlJRbWMzT0hkQlVVMUZTMFJrYUU1WFVYaE9lbXN6VDBSQmVrOUVWVEphYWxrMFdUSkdhVnBYU21sWk1rNXJDazlVUlRGTlYxcHFUVmRLYTFwcVpHdE5WMGwzU0VGWlMwdDNXVUpDUVVkRWRucEJRa0pCVVU5Uk0wcHNXVmhTYkVsR1NteGlSMVpvWXpKVmQweFJXVXNLUzNkWlFrSkJSMFIyZWtGQ1FsRlJabGt5YUdoaFZ6VnVaRmRHZVZwRE1YQmlWMFp1V2xoTmRsb3llSEJaYlUxMFdraHNkVmxYTVhCWmVrRmtRbWR2Y2dwQ1owVkZRVmxQTDAxQlJVZENRVGw1V2xkYWVrd3lhR3haVjFKNlRESXhhR0ZYTkhkbldXOUhRMmx6UjBGUlVVSXhibXREUWtGSlJXWkJValpCU0dkQkNtUm5SR1JRVkVKeGVITmpVazF0VFZwSWFIbGFXbnBqUTI5cmNHVjFUalE0Y21ZclNHbHVTMEZNZVc1MWFtZEJRVUZaVTJOMWVIUnZRVUZCUlVGM1FrZ0tUVVZWUTBsRU5sWm5kRGt5TmxSQmJISjRPRzVLU1dwckwyeE1TWGxIUXpCdWRFVlNTMXB5ZFdGa2VFVkdkbU5GUVdsRlFYSlJTM1YzVFVab09FaGpSZ3BOVkRJNVFqUTJORkZxVEc5Vk1EVmFMM2N6TVM5WFNVaEtaV2RCYVRGSmQwTm5XVWxMYjFwSmVtb3dSVUYzVFVSaFVVRjNXbWRKZUVGT1JGSkdaalpZQ2t3MEwzWkpaMFZFTW1GU1pHVTNhakpCU1U1dWFFMUxWVFJwU21ORWJ5OW1OVXBxWVc1MFR5dHdWbGd4VmxVck1rUktTbEIwYzJzMkwzZEplRUZMWmprS0wwWkxWV1kyYUd0blNWUTRkME5TYUVka1UzQnFaMkp1VlVObFMyMXFWMW9yTTNOeGJHeDZjamh1Y1N0d1FVSTBObk50SzFBMFRFUXZVbTlOUlVFOVBRb3RMUzB0TFVWT1JDQkRSVkpVU1VaSlEwRlVSUzB0TFMwdENnPT0ifX19fQ==",
          "integratedTime": 1669076822,
          "logIndex": 7577091,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/glibc-dynamic/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/glibc-dynamic",
      "githubWorkflowSha": "7a5d1797803856f68cabebbccd9151fc1bdf7d1b",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3519258150",
      "sha": "7a5d1797803856f68cabebbccd9151fc1bdf7d1b"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

