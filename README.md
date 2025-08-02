# UPX - Wrapper para Delphi (via BOSS)

Este repositório é um **wrapper** contendo apenas o executável do [UPX (Ultimate Packer for eXecutables)](https://upx.github.io/), versão **5.0.2**, preparado para ser usado como **dependência via BOSS** em projetos Delphi.

> Ideal para compactar automaticamente executáveis após o build, usando os **Build Events** do Delphi.

---

## 📦 Sobre o UPX

**UPX** é um compactador de executáveis de alto desempenho. Ele reduz o tamanho de arquivos `.exe` mantendo-os totalmente funcionais e executáveis de forma transparente.

- Projeto original: https://github.com/upx/upx
- Versão incluída neste wrapper: `5.0.2`
- Binário original retirado de:  
  https://github.com/upx/upx/releases/download/v5.0.2/upx-5.0.2-win32.zip

---

## 🔧 Estrutura

Este wrapper contém:

```
/
├── boss.json
└── bin/
    └── upx.exe  ← Executável do UPX (versão 5.0.2 para Windows 32-bit)
```

---

## 🚀 Como usar no seu projeto Delphi com BOSS

### 1. Instale com BOSS:

```bash
boss install github:seuusuario/upx-boss-wrapper
```

> Substitua `seuusuario` pelo nome do seu GitHub.

---

### 2. Configure o Build Event no Delphi

Acesse:

```
Project > Options > Build Events > Post-Build Event
```

Adicione o seguinte comando:

```cmd
"$(PROJECTDIR)modules\upx\bin\upx.exe" --best --lzma "$(OUTPUTDIR)$(OUTPUTNAME).exe"
```

Marque para executar `On successful build`.

---

## 🧪 Teste de compactação

Você pode testar manualmente a compactação do seu executável:

```bash
modules\upx\bin\upx.exe --test MeuApp.exe
```

---

## ⚠️ Avisos

- UPX pode causar falso positivo em antivírus. Use com cautela em ambientes sensíveis.
- Compactar arquivos com `--lzma` ou `--ultra-brute` pode aumentar bastante o tempo de build.
- Recomendado usar apenas em builds **Release**.

---

## 📄 Licença

Este wrapper segue a [licença do UPX original (GPL)](https://github.com/upx/upx/blob/devel/LICENSE).  
Este repositório apenas redistribui o binário oficial para facilitar a automação com Delphi.

---
