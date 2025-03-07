## Setup

Please install [teensy_loader_cli](https://github.com/PaulStoffregen/teensy_loader_cli) 
```shell
rustup target add thumbv7em-none-eabihf
cargo install cargo-binutils
rustup component add llvm-tools-preview
```

## Flash
Programs teensy 4.1. Make sure to press program button
```shell
cargo build --release
cargo objcopy --release -- -O ihex controller.hex
teensy_loader_cli --mcu=TEENSY41 -w controller.hex
```

## Monitor
Read over screen (linux)
```shell
sudo screen /dev/ttyACM0 9600
```