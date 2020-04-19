# Pesy With Luv

First make sure you have [`esy`](https:/esy.sh) and [`pesy`](https://github.com/esy/pesy) installed and updated.

```sh
npm i -g esy
npm i -g pesy
```

Then create a directory, `cd` into it, then run `pesy` and follow the prompts.

```sh
mkdir pesy-with-luv && cd pesy-with-luv
```


**Contains the following libraries and executables:**

```
pesy-with-luv@0.0.0
│
├─test/
│   name:    TestPesyWithLuv.exe
│   main:    TestPesyWithLuv
│   require: pesy-with-luv.lib
│
├─library/
│   library name: pesy-with-luv.lib
│   namespace:    PesyWithLuv
│   require:
│
└─executable/
    name:    PesyWithLuvApp.exe
    main:    PesyWithLuvApp
    require: pesy-with-luv.lib
```

## Build The Project:

```
esy install
esy build
```

## Running It:

After building the project, you can run the main binary that is produced.

```
esy x PesyWithLuvApp.exe
```

## Adding the Luv library

Let's install [`luv`](https://github.com/aantron/luv).

Run `esy add @opam/luv`

Then go to `package.json` and add `"require": ["luv"]` to the `library` key.

```json
    "library": {
      "name": "pesy-with-luv.lib",
      "namespace": "PesyWithLuv",
     add this-> "require": [
        "luv"
      ]
    },
```

Run `esy pesy` to rebuild. 

Note that your `dune` file in `library/dune` has changed to reflect the added `luv` library.

This is great if you not comfortable with `dune` files yet.

Now you can call `PesyWithLuv.Demo.luv();` in `executable/PesyWithLuvApp.re`;

Run `esy x PesyWithLuvApp.exe` then watch the output.

## Running Binary:

After building the project, you can run the main binary that is produced.

```
esy x PesyWithLuvApp.exe
```


```
~/Github/pesy-with-luv
❯ esy x PesyWithLuvApp.exe

pesy-with-luv@0.0.0

  Build Succeeded! To test a binary:

      esy x PesyWithLuvApp.exe


Hello
33%
66%
Done
```
