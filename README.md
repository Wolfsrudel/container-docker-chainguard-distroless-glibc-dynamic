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
| `migration` `migration-20221119` | `sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:dc022e6e10500cb7e49c2bf7af59b3ae14d57f49fae32152fc62b4bc97167be6) | `amd64` |
| `latest` | `sha256:8386d826a73d9818efa3d58cb8473a104c96a2ff990034bd8ad79ef91c39e8c9`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:8386d826a73d9818efa3d58cb8473a104c96a2ff990034bd8ad79ef91c39e8c9) | `amd64` |
| `migration-20221118` | `sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:cf9690c4cc99d81adbadd64683c82c2eb3ec778cab279b5eff793b93774e19fa) | `amd64` |



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
        "docker-manifest-digest": "sha256:8386d826a73d9818efa3d58cb8473a104c96a2ff990034bd8ad79ef91c39e8c9"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "7887be0e1d6fd381f6c4cdd2063dba87a438f760",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/glibc-dynamic",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEYCIQDyqZTLmPrjPgoMDSEkgYiy9toZXtSqFVJCN5B7DzsvQQIhAPIIf7ZEy8YWFMRf5FkLx8NH/poWKpM4oOfuBQeWJDBd",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIyOTk5NTU1YjJmYzlhN2QxYzkyMDE1MmE5NmRiZGYwNTQ5Mjg2Y2FkMWRjOWM0NWM4NDc3NzlhMmFlYmY1Yjg1In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJUUNrTGpxMkFkZitsamlwMUF6SldzS3FVOGppU2VpM3RnUmxKQ0lpVG5qZUpBSWdDMEt4L2NJaFZNQk82amx5RmZuRjRtSzJUSGRKRWR0YVprNnhGb2dIa21vPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUjFla05EUVRCRFowRjNTVUpCWjBsVlpEVTVTSFozVGpnd2JuVm5iakIwV1ZSVmIwbGtkbmh4U2xZd2QwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVUlRWTlJFbDNUVlJCTUZkb1kwNU5ha2w0VFZSRk5VMUVTWGhOVkVFd1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZOUjJSVU5qWjJhVlJuYjJGYVowOXRVbFZzV2t3MFJtTnhVbFl4TDFodUwyZFhZbWtLTUVNeVdWUjJlbFpVVUhoR1lVOVJRVmhQYVVRclFVeFRhRGRNZGtKS0szTlBNWEpoV0ZRM1ZGWlRPRFF2YUdRdmFFdFBRMEZzT0hkblowcGlUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZZU0c1R0NuWlJabmt2Y1d4dlYwNVJObXR4TkZaWU5EQTVVakZGZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDJKM1dVUldVakJTUVZGSUwwSkhWWGRaTkZwb1lVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5WkhOaFYwcHFURmRTTldKdFJuUmhWMDEyVEcxa2NHUkhhREZaYVRrellqTktjbHB0ZUhaa00wMTJZMjFXYzFwWFJucGFVelUxQ2xsWE1YTlJTRXBzV201TmRtRkhWbWhhU0UxMllsZEdjR0pxUVRWQ1oyOXlRbWRGUlVGWlR5OU5RVVZDUWtOMGIyUklVbmRqZW05MlRETlNkbUV5Vm5VS1RHMUdhbVJIYkhaaWJrMTFXakpzTUdGSVZtbGtXRTVzWTIxT2RtSnVVbXhpYmxGMVdUSTVkRTFDV1VkRGFYTkhRVkZSUW1jM09IZEJVVWxGUTBoT2FncGhSMVpyWkZkNGJFMUVXVWREYVhOSFFWRlJRbWMzT0hkQlVVMUZTMFJqTkU5RVpHbGFWRUpzVFZkUk1scHRVWHBQUkVadFRtMU5NRmt5VW10TmFrRXlDazB5VW1sWlZHY3pXVlJSZWs5SFdUTk9ha0YzU0VGWlMwdDNXVUpDUVVkRWRucEJRa0pCVVU5Uk0wcHNXVmhTYkVsR1NteGlSMVpvWXpKVmQweFJXVXNLUzNkWlFrSkJSMFIyZWtGQ1FsRlJabGt5YUdoaFZ6VnVaRmRHZVZwRE1YQmlWMFp1V2xoTmRsb3llSEJaYlUxMFdraHNkVmxYTVhCWmVrRmtRbWR2Y2dwQ1owVkZRVmxQTDAxQlJVZENRVGw1V2xkYWVrd3lhR3haVjFKNlRESXhhR0ZYTkhkbldYTkhRMmx6UjBGUlVVSXhibXREUWtGSlJXWlJVamRCU0d0QkNtUjNSR1JRVkVKeGVITmpVazF0VFZwSWFIbGFXbnBqUTI5cmNHVjFUalE0Y21ZclNHbHVTMEZNZVc1MWFtZEJRVUZaVTA1dWFYZzNRVUZCUlVGM1Fra0tUVVZaUTBsUlJGSlVTazB5V210QlVXVnVVMlpqWm1wMmJGTTJaMWMzT1U4NE1XdDZkRk5LVEhOb1UzQlJiM1pzT1VGSmFFRktlV0Y2V1VFd1pHZDRWd3BqWW5VMGJIUjJXRVJ0UldWelNtTlNVelpyUlRaQlIyMXpWVVJyY0ZrdlkwMUJiMGREUTNGSFUwMDBPVUpCVFVSQk1tdEJUVWRaUTAxUlF5dFdSbTFKQ2xGa1pVa3paREpPTjJ4aVlVeFhXSGhGY25aRGFuUXlhWE5CTlVsMVRDdDBRV2hJVGxRd05rMVpVR3ByWkV4a2FXTm1VU3M1ZFVZMWVUZE5RMDFSUTFrS2VHTkRZalZCWjNvdlUwZFlUbVJSVjBWQ2N5dFNXQzlHS3l0RVpETnFNRVpFYTNjMlptVk5SMGh4VFhGRlMyZFFSbVIzYjFSMWVFVkdlWGhVZWpSM1BRb3RMUzB0TFVWT1JDQkRSVkpVU1VaSlEwRlVSUzB0TFMwdENnPT0ifX19fQ==",
          "integratedTime": 1668823267,
          "logIndex": 7386490,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/glibc-dynamic/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/glibc-dynamic",
      "githubWorkflowSha": "7887be0e1d6fd381f6c4cdd2063dba87a438f760",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3501564524",
      "sha": "7887be0e1d6fd381f6c4cdd2063dba87a438f760"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

