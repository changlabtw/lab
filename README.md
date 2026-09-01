# changlabtw / lab

生物資料科學實驗室網站 —— <https://changlabtw.github.io/lab/>

## 這個 repo 的內容是產生出來的，不要直接改

`*.qmd`、`_quarto.yml`、`styles.css` 全部由私有知識庫
`changlab-research-os` 的 `core/publish.py` 產生。在這裡手改，
下次匯出就會被蓋掉。

改內容請到知識庫：

| 想改什麼 | 改哪裡 |
|---|---|
| 頁面內容 | `domains/site/pages/*.md` |
| 導覽列順序、標籤 | 各頁 front-matter 的 `nav:` |
| 站台標題、佈景、網址 | `domains/site/domain.yml` 的 `site:` |

然後在知識庫執行：

```bash
make check
python core/publish.py          # 匯出到這個 repo
git -C ../changlabtw-lab add -A && git -C ../changlabtw-lab commit && git push
```

不受匯出影響、可以在這裡直接維護的只有：
`README.md`、`.gitignore`、`.github/`。

## 部署

push 到 `main` → GitHub Actions 跑 `quarto render` → 部署到 GitHub Pages。
本機不需要安裝 Quarto。

**首次設定**：repo Settings → Pages → Source 選 **GitHub Actions**。

## 網址架構

`changlabtw.github.io` 的根命名空間留給工具的 project site
（`/wpSBOOT/`、`/GODoc/` …），一個 repo 一個路徑段，所以網站放在 `/lab/`。
根目錄由 `changlabtw.github.io` repo 提供導引頁。
