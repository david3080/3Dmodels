# このアプリについて

このアプリケーションは、さまざまな3Dモデルのコレクションを展示するために設計されたウェブアプリケーションです。Googleの`<model-viewer>`ウェブコンポーネントを利用して、インタラクティブな3Dモデル表示とAR（拡張現実）機能を提供します。

現在、以下のカテゴリの3Dモデルを閲覧できます。

*   像 (Statues)
*   靴 (Shoes)
*   家具 (Furniture)
*   動物 (Animals)

# 3Dモデル

model-viewerで表示するために準備した3Dモデル

## 靴
- shoe1 https://model3d.shopifycdn.com/models/o/31f14f245b24624b/1021_380MistHighRes.glb
- shoe2 https://github.com/drcmda/floating-shoe/blob/master/public/shoe-draco.glb
- shoe3 https://github.com/Shopify/screenshot-glb/blob/master/test/fixtures/shoe.glb

## 動物
https://github.com/Shadow60539/zoo_app/tree/master/assets

## 家具

https://free3d.com/3d-models/obj-furniture

## Model Viewerについて
https://webar-lab.palanar.com/developer/model-viewer/

## カスタムコード
```
model_viewer_plus: ^1.3.3
```

```
import 'package:model_viewer_plus/model_viewer_plus.dart';
class MViewer extends StatefulWidget {
  const MViewer({
    Key? key,
    this.width,
    this.height,
    required this.urlofglb,
  }) : super(key: key);

  final double? width;
  final double? height;
  final String urlofglb;

  @override
  _MViewerState createState() => _MViewerState();
}

class _MViewerState extends State<MViewer> {
  @override
  Widget build(BuildContext context) {
    return ModelViewer(
      backgroundColor: Color.fromARGB(0xFF, 0xEE, 0xEE, 0xEE),
      src: widget.urlofglb,
      ar: true,
      arModes: ['scene-viewer', 'webxr', 'quick-look'],
      autoRotate: true,
      cameraControls: true,
    );
  }
}
```