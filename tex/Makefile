# ============================================================
# Makefile — LuaLaTeX 授業プリント ビルド設定
#
# 使い方:
#   make          → PDF をビルド (out/main.pdf)
#   make clean    → 中間ファイルを削除
#   make open     → ビルド後 PDF を開く (WSL: Windows側のAcrobat/Edge)
#   make watch    → ファイル変更を監視して自動ビルド
# ============================================================

MAIN      = src/main.tex
OUTDIR    = out
PDFNAME   = $(OUTDIR)/main.pdf
LATEXMK   = latexmk
ENGINE    = -lualatex

# latexmk オプション
LATEXMK_FLAGS = \
	$(ENGINE) \
	-outdir=$(OUTDIR) \
	-interaction=nonstopmode \
	-file-line-error \
	-synctex=1

.PHONY: all clean open watch help

## デフォルト: PDF ビルド
all: $(OUTDIR)
	$(LATEXMK) $(LATEXMK_FLAGS) $(MAIN)
	@echo ""
	@echo "✅ ビルド完了: $(PDFNAME)"

## out ディレクトリ作成
$(OUTDIR):
	mkdir -p $(OUTDIR)

## クリーン (中間ファイル削除、PDFは残す)
clean:
	$(LATEXMK) -outdir=$(OUTDIR) -c $(MAIN)
	@echo "🧹 中間ファイルを削除しました"

## フルクリーン (PDF も削除)
distclean:
	$(LATEXMK) -outdir=$(OUTDIR) -C $(MAIN)
	rm -rf $(OUTDIR)
	@echo "🧹 out/ ディレクトリを削除しました"

## PDF を開く (WSL → Windows Explorer 経由)
open: all
	@if [ -f "$(PDFNAME)" ]; then \
		explorer.exe "$$(wslpath -w $(CURDIR)/$(PDFNAME))" 2>/dev/null || \
		xdg-open "$(PDFNAME)" 2>/dev/null || \
		echo "PDF: $(PDFNAME)"; \
	fi

## ファイル監視して自動ビルド
watch:
	$(LATEXMK) $(LATEXMK_FLAGS) -pvc $(MAIN)

## ヘルプ
help:
	@echo "利用可能なコマンド:"
	@echo "  make          → PDF ビルド"
	@echo "  make clean    → 中間ファイル削除"
	@echo "  make distclean→ 全出力削除"
	@echo "  make open     → ビルドしてPDFを開く"
	@echo "  make watch    → 変更監視・自動ビルド"
