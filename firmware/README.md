# Versioning

Firmware versions follow [semantic versioning](https://semver.org/) rules.
The [c++ driver](https://github.com/kobuki-base/kobuki_core) 
checks for compatibility between the software (i.e. driver) and firmware.
Firmware versions are of the form M.m.p:

- M(ajor) versions typically break protocol compatibility. When driver and firmware are incompatible, the driver will emit an error, suggest the required update and shutdown.
- m(inor) versions add features, but the protocol will have not been modified. When driver and firmware are incompatible, the driver will emit a warning and suggest the required update, but continue working.
- p(atch) versions provide minor bugfixes, but do not break driver or protocol compatibility.

The [c++ driver](https://github.com/kobuki-base/kobuki_core) provides a utility for
checking the version that is running on your kobuki. It will also provide versioning
information for the driver (software) and hardware:

```
  $ kobuki_version_info
    Version Info:
     * Hardware Version: 1.0.4
     * Firmware Version: 1.2.0
     * Software Version: 1.0.0
     * Unique Device ID: 97713968-842422349-1361404194
```

Additionally, firmware binaries come in three flavours:

* *latest*: most recent, but be aware that this version hasn't been tested much
* *stable*: more recent than factory and reasonably well tested
* *factory*: flashed onto the robots at the factory, has undergone stress testing

These are identified by the trailing suffix on binary filenames stored here.

More details on the specific features / fixes provided by each version can be found
in the [CHANGELOG](../CHANGELOG.rst).
