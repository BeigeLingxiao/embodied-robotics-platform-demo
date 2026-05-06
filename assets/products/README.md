# 产品素材目录规范

`assets/products` 作为产品素材与产品元数据的主目录，建议按“一个产品一个文件夹”的方式管理。

## 目录结构

```text
assets/products/
├─ catalog.json
├─ README.md
├─ Intel RealSense D435 深度相机/
│  ├─ product.json
│  ├─ image.png
│  └─ Intel RealSense D400 系列深度相机.pdf
├─ RH-JM-17 机器人关节电机/
│  ├─ product.json
│  └─ image.jpg
└─ ...
```

## 单品目录规则

每个产品目录建议包含：

1. `product.json`
   保存该产品的基础信息与本目录内文件引用。
2. `image.*`
   默认主图，优先使用白底或浅底的 4:3 产品主图。
3. `*.pdf`
   产品手册、数据手册、宣传册等文档。

## product.json 字段建议

```json
{
  "id": "part_003",
  "aliases": ["part_016"],
  "name": "Intel RealSense D435 深度相机",
  "model": "D435",
  "brand": "Intel RealSense",
  "category": "深度相机",
  "image": "image.png",
  "manuals": [
    {
      "name": "Intel RealSense D400 系列深度相机",
      "file": "Intel RealSense D400 系列深度相机.pdf"
    }
  ]
}
```

## catalog.json 作用

`catalog.json` 用于汇总产品目录与元数据文件入口，适合作为后续批量生成、校验、索引构建的主清单。

## 当前策略

当前 demo 里：

- 有真实产品目录素材的，优先引用 `assets/products/<产品目录>/...`
- 暂时没有完整目录素材的，仍允许回退到 `assets/images/...`

后续建议逐步把所有产品图与手册都迁入 `assets/products`，让这里成为唯一可信的产品素材源。
