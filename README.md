# codontest

mjx-playground3 で speedeval.py を動かしたかったんですが上手く codon がモジュールを認識してくれなかったので poetry で新しく環境を作り直したら動いた。

**this project is archived. because speed-test is now impl shanten-playground.**

```
poetry new codontest
cd codontest
poetry shell
poetry add numpy
___
from python import numpy as np
___
としてcodonを実行したら上手く動いた。
codon run helloworld.py
```

ただあれですね、from python import numpy as np とか書きかえが必要なのはだるい

https://zenn.dev/turing_motors/articles/e23973714c3ecf#%E3%81%AA%E3%81%9Ccodon%E3%81%AF%E3%81%93%E3%82%8C%E3%81%BB%E3%81%A9%E9%AB%98%E9%80%9F%E3%81%AA%E3%81%AE%E3%81%8B

マジ？

```
一方、外部ライブラリ（例えばnumpyやpandasなど）を利用する場合は型の関係上、Codonでは外部ライブラリを含めたままコンパイルすることができません。Pythonコードとして明示的に分離する必要があり、その点はさらに簡単になるとよいなと感じました。このあたりは今も開発が進められているようです。

注意点として、CodonのライセンスはBusiness Source Licenseであり、非商用であれば自由に使用することが可能です。また、2025年11月以降であればApache License 2.0に移行するため、企業での利用シーンも増えていくかもしれません。
```

## speedtest.py

## uvに移行時にエラーが出た
mac
```
❯ codon run -release hello.py 
CError: dlopen(libpython.dylib, 0x0002): tried: 'libpython.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OSlibpython.dylib' (no such file), '/Users/user/.codon/bin/libpython.dylib' (no such file), '/Users/user/.codon/bin/../lib/codon/libpython.dylib' (no such file), '/usr/lib/libpython.dylib' (no such file, not in dyld cache), 'libpython.dylib' (no such file)

Raised from: std.internal.dlopen.dlopen.2:0
/Users/user/.codon/lib/codon/stdlib/internal/dlopen.codon:31:9
zsh: abort      codon run -release hello.py
aituber-win-py3.12
```