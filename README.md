# esp_usrsctp

Userspace [SCTP](https://datatracker.ietf.org/doc/html/rfc4960) stack ([usrsctp](https://github.com/sctplab/usrsctp)) port for ESP-IDF.

Used for WebRTC data channels and other SCTP-based protocols on ESP32-series chips.

## Features

- usrsctp pinned at fork commit `32bb935` (vikramdattu/usrsctp)
- LWIP integration (built with `SCTP_USE_LWIP`)
- ESP-specific patches:
  - SPIRAM stack allocation for usrsctp threads
  - Thread-safe netif API support
  - sin6 overflow fix
  - LWIP support layer

## Add to a project

```bash
idf.py add-dependency "vikramdattu/esp_usrsctp^1.0.0"
```

Or in your project's `main/idf_component.yml`:

```yaml
dependencies:
  vikramdattu/esp_usrsctp: "^1.0.0"
```

## Supported targets

esp32, esp32s2, esp32s3, esp32c3, esp32c5, esp32c6, esp32p4. Requires ESP-IDF >= 5.4.

## Source

This wrapper bundles a fork of [sctplab/usrsctp](https://github.com/sctplab/usrsctp) as a submodule (vikramdattu/usrsctp). The fork carries ESP-specific patches on top of upstream.

## License

BSD-3-Clause (see `LICENSE.md`), matching upstream usrsctp.
