# Miyagase-animal-sign-map
# 宮ヶ瀬ダム周辺における動物注意標識とロードキル分布の分析  
*A spatial study of wildlife warning signs and roadkill incidents around Lake Miyagase*

---

##  プロジェクト概要
本研究では、宮ヶ瀬ダム周辺の道路に設置された「動物注意」標識の位置を  
**OpenStreetMap（OSM）** に登録し、  
**QGIS** を用いてロードキル発生位置との関係を可視化・分析する。 

目的は以下：

- 地域の道路安全および生態系保全に資するデータの作成  
- OSMを活用したオープンデータ研究の実践  
- GitHubによる再現性の高い研究フローの構築  

---

## 研究手順

### 1️データ収集
- **使用アプリ**：OSMAnd / StreetComplete  
- **登録方法**：
- 現地で標識を確認し、撮影＋GPS記録とともにOSMへ投稿。  

---

###  データ抽出（Overpass Turbo）
- **クエリ例**：
```overpass
[out:json][timeout:25];
node["traffic_sign"="JP:W8"](35.45,139.1,35.6,139.35);
out body;
id,date,species,latitude,longitude,source
001,2024-10-12,deer,35.5152,139.2405,kanagawa_pref
002,2024-10-21,boar,35.4988,139.2557,survey
miyagase-animal-sign-map/
│
├─ data/
│   ├─ osm_signs.geojson
│   ├─ roadkill_2024.csv
│   └─ boundaries.geojson
│
├─ analysis/
│   ├─ qgis_project.qgz
│   └─ scripts/
│        └─ spatial_analysis.py
│
├─ docs/
│   ├─ report.md
│   ├─ figures/
│   │    ├─ map_overview.png
│   │    └─ heatmap_density.png
│   └─ presentation.pptx
│
├─ photos/
│   ├─ deer_sign_001.jpg
│   └─ boar_sign_002.jpg
│
├─ LICENSE
├─ README.md
└─ .gitignore
