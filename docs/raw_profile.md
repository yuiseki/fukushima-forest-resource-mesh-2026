# Raw profile of the 69 sheets that touch Fukushima (whole sheets, before any cutting)

Source: G空間情報センター dataset `mesh_9` (全国森林資源メッシュ, zone IX), sheets chosen by intersecting the sheet index with the Fukushima boundary (KSJ N03). Run 2026-10-29; sha256 of each archive is in data/raw/20261029/MANIFEST.json (kept in the Hugging Face repo).

These counts cover the whole sheets, so they include cells of neighbouring prefectures and of the sea. The Fukushima-only figures are in docs/fukushima_profile.md.

- sheets: 69; rows: 39,939,045; layers: 69 geometry layers, one per file, named like the file; geometry type ids: {6: 39939045} (6 = MultiPolygon); invalid geometries: 0
- CRS: EPSG:6677; plane bbox x -60000 to 107260, y 75000 to 219420
- column sets: 1 distinct (林種, 森林簿樹種1, 森林簿樹種2, 森林簿樹種3, 林齢, 森林簿年月日, 樹冠高, レーザ解析樹種, 立木密度, 平均標高, 計測年月日, plus the GeoPackage fid)

| column | NULL rows | share of rows |
| --- | ---: | ---: |
| 林種 | 9,457,405 | 23.7% |
| 森林簿樹種1 | 9,457,405 | 23.7% |
| 森林簿樹種2 | 29,087,519 | 72.8% |
| 森林簿樹種3 | 33,520,515 | 83.9% |
| 林齢 | 9,457,405 | 23.7% |
| 森林簿年月日 | 9,457,406 | 23.7% |
| 樹冠高 | 39,939,045 | 100.0% |
| レーザ解析樹種 | 39,939,045 | 100.0% |
| 立木密度 | 39,939,045 | 100.0% |
| 平均標高 | 39,939,045 | 100.0% |
| 計測年月日 | 39,939,045 | 100.0% |

## Unique values of the text columns (all 69 sheets)

### 林種

| value | rows |
| --- | ---: |
| 天然林 | 18,228,312 |
| 人工林 | 10,917,913 |
| <NULL> | 9,457,405 |
| その他 | 1,028,144 |
| 伐採跡地 | 138,533 |
| 未立木地 | 103,239 |
| 竹林 | 65,499 |

### 森林簿樹種1

| value | rows |
| --- | ---: |
| 広葉樹 | 16,492,220 |
| <NULL> | 9,457,405 |
| スギ | 6,291,158 |
| マツ類 | 3,731,997 |
| ヒノキ類 | 1,078,525 |
| カラマツ | 934,421 |
| その他 | 898,447 |
| その他針葉樹 | 820,349 |
| 伐採跡地 | 138,456 |
| タケ | 65,499 |
| ヒバ | 30,568 |

### 森林簿樹種2

| value | rows |
| --- | ---: |
| <NULL> | 29,087,519 |
| 広葉樹 | 7,116,668 |
| マツ類 | 1,091,760 |
| スギ | 1,011,636 |
| その他針葉樹 | 728,699 |
| ヒノキ類 | 596,502 |
| カラマツ | 194,886 |
| ヒバ | 111,209 |
| 伐採跡地 | 71 |
| エゾマツ | 47 |
| その他 | 45 |
| 11       101 | 1 |
| 育成単層 | 1 |
| 101広葉樹 | 1 |

### 森林簿樹種3

| value | rows |
| --- | ---: |
| <NULL> | 33,520,515 |
| 広葉樹 | 3,328,281 |
| マツ類 | 1,493,308 |
| その他針葉樹 | 874,605 |
| スギ | 355,559 |
| ヒノキ類 | 168,458 |
| カラマツ | 101,212 |
| ヒバ | 97,107 |

### レーザ解析樹種

| value | rows |
| --- | ---: |
| <NULL> | 39,939,045 |

### 森林簿年月日

| value | rows |
| --- | ---: |
| 2024/4/1 | 16,328,606 |
| <NULL> | 9,457,406 |
| 2022/4/1 | 5,223,120 |
| 2020/4/1 | 2,379,900 |
| 2023/4/1 | 2,231,727 |
| 2021/4/1 | 1,770,174 |
| 2019/4/1 | 1,416,070 |
| 2021/3/31 | 827,990 |
| 2024/3/31 | 304,052 |

## Other findings

- 計測年月日 values other than NULL: {}
- The literal text `#N/A` as a value: 森林簿樹種1 0 rows, 森林簿樹種2 0 rows; kept as in the source.
- 林齢 is 0 in 1,102,793 rows besides the NULLs (9,457,405); whether 0 means an age of zero or an unknown age is not stated in the definition.
- 森林簿年月日 holds 8 dates, as text: 2019/4/1, 2020/4/1, 2021/3/31, 2021/4/1, 2022/4/1, 2023/4/1, 2024/3/31, 2024/4/1.
- No column separates 国有林 from 民有林 in the mesh; that attribute (民国別) is in the 森林計画対象森林レイヤ of Fukushima (downloaded as well).
