# WARSAW Archlinux package


> :warning: This project is currently not being maintained.
> You can fork it and change according, and/or take a look
> at https://aur.archlinux.org/packages/warsaw

This package install the [warsaw][2] software libs and daemon on an 
[Archlinux][1] system.

This is the program provided by [Caixa Econômica Federal][3] for extra security
and called _Módulo Adicional de Segurança CAIXA_. There is no guarantee that it'll work for other banks.

:warning: Notice that this package does not includes any software. All files
are downloaded from original sources during build process.

## Installing

```console
git clone https://github.com/paulodiovani/AUR-warsaw-cef.git warsaw-cef
cd warsaw-cef
makepkg -sri
```

[1]: https://www.archlinux.org
[2]: http://www.gastecnologia.com/suporte/warsaw
[3]: http://www.caixa.gov.br/

