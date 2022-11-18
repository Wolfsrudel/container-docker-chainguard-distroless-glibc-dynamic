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
| `latest` | `sha256:a5881c17952a7fcb0dc627f643eed27135e02fd01a1a7756398ae0fe4d390ffc`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:a5881c17952a7fcb0dc627f643eed27135e02fd01a1a7756398ae0fe4d390ffc) | `amd64` |



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
        "docker-manifest-digest": "sha256:a5881c17952a7fcb0dc627f643eed27135e02fd01a1a7756398ae0fe4d390ffc"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "dbcf899697a394a3bcab8c84a0b625043b7ea9fd",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/glibc-dynamic",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCIEjNV9J7vJMthtA+QQ5DFxNuNuq24TAw4dOOQQyfdLfLAiBh0ckRHs/1HL6b/F47q+z/T6NTVsbsJuhioxUnXyRr4w==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiI5ZDkyOTRiMzE5OGJjYWMyMDk4YjNiMDBkMjFkZGRkYjcwZDE3YzY1NjU2NDk1ZmY3Yzg1ZjMwMGM0YzM2MzRlIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FWUNJUUN5cmdEWFh2eXdDbWxSTUQ2TG5vVTB2dmRHWWJoek5LNWM0K3l1UUdMNG9RSWhBS0VTR096ak0wTzJDT3lZcFAvQUhkbnlOY3FnNUV4ajN5ZVU3SWJIbVV3VCIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUjFWRU5EUVhvclowRjNTVUpCWjBsVlZUbFdUbmxCWjNSelYzaFVSRzB2ZURWa1JHVnVha2czYnpCdmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVUlRSTlJFbDNUMFJSZWxkb1kwNU5ha2w0VFZSRk5FMUVTWGhQUkZGNlYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVV5Wm5GTFoybHFabmR6ZUdobEsyVk5iM1kwUnpWUFNVbG5OeTlqU200NVRURnljRTRLYTFjeU0xQlNWWE5oZVdKNmNVdE9lVmRCT1dWVFQwZDFkRVExUnpkV2RYaGpNVUZSVW14cUt6SkhjbTR4TWtoakszRlBRMEZzTkhkblowcGhUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZRT0ZaakNtWXZkR3RvWlhkRGJHVnJPVEpsVnpZNVRWZ3pXbVF3ZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDJKM1dVUldVakJTUVZGSUwwSkhWWGRaTkZwb1lVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5WkhOaFYwcHFURmRTTldKdFJuUmhWMDEyVEcxa2NHUkhhREZaYVRrellqTktjbHB0ZUhaa00wMTJZMjFXYzFwWFJucGFVelUxQ2xsWE1YTlJTRXBzV201TmRtRkhWbWhhU0UxMllsZEdjR0pxUVRWQ1oyOXlRbWRGUlVGWlR5OU5RVVZDUWtOMGIyUklVbmRqZW05MlRETlNkbUV5Vm5VS1RHMUdhbVJIYkhaaWJrMTFXakpzTUdGSVZtbGtXRTVzWTIxT2RtSnVVbXhpYmxGMVdUSTVkRTFDV1VkRGFYTkhRVkZSUW1jM09IZEJVVWxGUTBoT2FncGhSMVpyWkZkNGJFMUVXVWREYVhOSFFWRlJRbWMzT0hkQlVVMUZTMGRTYVZreVdUUlBWR3N5VDFSa2FFMTZhekJaVkU1cFdUSkdhVTlIVFRST1IwVjNDbGxxV1hsT1ZFRXdUVEpKTTFwWFJUVmFiVkYzU0VGWlMwdDNXVUpDUVVkRWRucEJRa0pCVVU5Uk0wcHNXVmhTYkVsR1NteGlSMVpvWXpKVmQweFJXVXNLUzNkWlFrSkJSMFIyZWtGQ1FsRlJabGt5YUdoaFZ6VnVaRmRHZVZwRE1YQmlWMFp1V2xoTmRsb3llSEJaYlUxMFdraHNkVmxYTVhCWmVrRmtRbWR2Y2dwQ1owVkZRVmxQTDAxQlJVZENRVGw1V2xkYWVrd3lhR3haVjFKNlRESXhhR0ZYTkhkbldXOUhRMmx6UjBGUlVVSXhibXREUWtGSlJXWkJValpCU0dkQkNtUm5SR1JRVkVKeGVITmpVazF0VFZwSWFIbGFXbnBqUTI5cmNHVjFUalE0Y21ZclNHbHVTMEZNZVc1MWFtZEJRVUZaVTBsbWRFZFpRVUZCUlVGM1FrZ0tUVVZWUTBsQmNGSnlWMWxEVHpWNFYyVTVTUzgxV0dsQlZUWk9hR2RUUVd0ekt6RllVVlpoYVdVMmRGaHpPRFF6UVdsRlFUaFBORmt2ZFRoaGIyWktkZ3BFWVhocFpXb3pkVWhvTjFabVRtcGxaVVJzYURWQ2FubHZVRmhyWm5kRmQwTm5XVWxMYjFwSmVtb3dSVUYzVFVSaFFVRjNXbEZKZUVGSk9XaFhNVGxtQ2k5cFNtUXlRbHBoVUhCbFVtWkxUMUZQYjA5dldEVkhXRmRFVkVKRVRWZGphWGhEWVVaQ2EyTlFURkpoT0dkQlVtRmxLM0YwTTJSS1MwRkpkMHhEU2tNS1RqUTNVMVpWY0ROYVppdFRXRTlsTTNwdFlta3pMekZMYVhWMksyWmhkMDl5YVhFeGFUVlpSbm9yYVRWVGRVcFJaRkY0TjFWd2RFRlVlV1V2Q2kwdExTMHRSVTVFSUVORlVsUkpSa2xEUVZSRkxTMHRMUzBLIn19fX0=",
          "integratedTime": 1668737327,
          "logIndex": 7313597,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/glibc-dynamic/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/glibc-dynamic",
      "githubWorkflowSha": "dbcf899697a394a3bcab8c84a0b625043b7ea9fd",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3493585098",
      "sha": "dbcf899697a394a3bcab8c84a0b625043b7ea9fd"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

