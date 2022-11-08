# RISC-V Vector Tests

RISC-V V-extension 1.0 has been frozen for a while, but there is currently no serious open source test suite available, and this project tries to fill that void.

The Spike simulator is known as the RISC-V gold standard simulator, and although we don't know how Spike is tested, it does fully support the V extension. So we can make a slight modification to Spike, and for any test, let it automatically generate a reference result for that test. This way, we can generate tests for all instructions almost automatically. Under this framework, all we have to do is write a simple config file for each instruction.

## How to use

```
make -j8
```

After `make`, you will find all the generated tests in `out/bin/stage2/`.

The default VLEN is 256, if you want to generate tests for a different VLEN/ELEN, you can use `make -e VLEN=512 ELEN=128 -j8`.

> NOTE: When changing VLEN and ELEN, you need to run `make` twice. The first run will regenerate the Makefrag file, and the second run will generate the tests.

## License

This project uses third-party projects, and the licenses of these projects are attached to the corresponding directories.

The code for this project is distributed under the MIT license.
