# Xdebug

## Install

Refer to [the documentation](https://xdebug.org/docs/install). 

On Mac, you can [install](https://xdebug.org/docs/install) with `pecl`.

```sh
pecl install xdebug
```

In the PHP environment you intend to use xdebug, add this line to PHP ini file:

```ini
zend_extension=xdebug.so
```

Verify installation by running `php -v` and checking for "with Xdebug" extension line.

## Profiling 

To profile, add configuration to PHP ini:

```ini
xdebug.mode = profile
xdebug.output_dir = /path/where/files/should/be/stored 
```

If you want finer control over when the profiling triggers, see the [documentation](https://xdebug.org/docs/profiler).

### Visualize Profiling 

To visualize the profiling output, use [`qcachegrind`](https://formulae.brew.sh/formula/qcachegrind). 

Install with HomeBrew:
```
brew install qcachegrind
```

Launch with `qcachegrind`. You may need to unpack the archived profiler output before opening it in the UI. 

This [short video](https://www.youtube.com/watch?v=h-0HpCblt3A) has an overview of the interface.