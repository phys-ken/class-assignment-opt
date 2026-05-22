# クラス替え最適化 — 授業資料

> 🤖 **このリポジトリは [Claude Code](https://claude.ai/code)（Anthropic）による
> WSL2 開発環境テストとして自動生成されたサンプルです。**  
> MkDocs / GitHub Pages / LuaLaTeX の動作確認を目的としており、
> 実際の授業資料ではありません。

整数計画法と Google OR-tools を使ったクラス替え最適化のデモ資料です。

🌐 **GitHub Pages**: https://phys-ken.github.io/class-assignment-opt/

## 📄 PDF

| 種別 | 場所 | URL |
|------|------|-----|
| MkDocs 版（WeasyPrint） | `docs/pdf/document.pdf` | [Pages から開く](https://phys-ken.github.io/class-assignment-opt/pdf/document.pdf) |
| TeX 版（LuaLaTeX） | `docs/pdf/handout-tex.pdf` | [Pages から開く](https://phys-ken.github.io/class-assignment-opt/pdf/handout-tex.pdf) |

## ローカルでの確認

```bash
mkdocs serve   # http://127.0.0.1:8000 で確認
```

## PDF 生成

```bash
# MkDocs PDF (site/pdf/document.pdf)
mkdocs build

# TeX PDF (tex/out/main.pdf)
cd tex && make
```

## ライセンス

CC BY 4.0
