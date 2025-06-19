# Prerequisites

- **Docker**: Ensure Docker is installed and running on your machine.
- **Fonts**: Place any required fonts in the `fonts/` directory.
- **Build Script**: The `build.sh` script must be present in the root directory.

# Building the Lambda Layer

Run the following Docker command from the `wkhtmltopdf-layer` directory:

```bash
docker run --rm \
  -v "$(pwd)/output":/output \
  -v "$(pwd)/fonts":/build/fonts \
  -v "$(pwd)/build.sh":/build/build.sh \
  -w /build \
  -it \
  --platform=linux/amd64 \
  amazonlinux:2023 \
  bash ./build.sh
```
