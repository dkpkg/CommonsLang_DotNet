# CommonsLang_DotNet

Standalone package repository for `CommonsLang_DotNet.SDK@10.0.100-rc.2.25502.107`.

## Updating generated workspace state

```sh
./dk0 update
```

## Validating the package

```sh
./dk0 --autofix -I etc/dk/v --trust-local-package CommonsLang_DotNet get-bundle CommonsLang_DotNet.SDK.Bundle@10.0.100-rc.2.25502.107 -d target/dotnetbundle
./dk0 --autofix -I etc/dk/v --trust-local-package CommonsLang_DotNet run-rule CommonsLang_DotNet.SDK.Files@10.0.100-rc.2.25502.107 -d target/dotnetsdk slot=Release.Windows_x86_64
```

## Regenerating distribution scripts

Generate the checked-in distribution script:

```powershell
.\dk0 -nosysinc --verbose distribute --library 'CommonsLang_DotNet@2.5.999911122233' --actual-in-place CommonsLang_DotNet-dist-any dist-any.u
```

Use CI to validate `dist-any.u` across the target ABI matrix.
