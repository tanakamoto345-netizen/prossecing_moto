# 課題タイトル：3Dプレイヤー移動

#学籍番号・氏名
・学籍番号　2501014
・氏名　田中望斗

## 📁 ファイル名
`sketch_251007b.pde`

## 📝 概要
Processingの3D描画機能（P3D）を使い、キーボード操作で動かせる立方体（プレイヤー）を実装しました。  
地面を描画し、カメラを固定視点にすることで簡易的な3D空間を表現しています。

## 🎮 操作方法
| キー | 動作 |
|------|------|
| W | 前進（Z軸 -） |
| S | 後退（Z軸 +） |
| A | 左移動（X軸 -） |
| D | 右移動（X軸 +） |
| Space | 上昇（ジャンプ） |
| Shift | 下降（しゃがみ） |

## 💻 コード
```java
float playerX = 0;
float playerY = 0;
float playerZ = 0;

void setup() {
  size(800, 600, P3D);
}

void draw() {
  background(150);

  // 視点（カメラ固定）
  camera(200, -200, 300, 0, 0, 0, 0, 1, 0);

  // 地面
  pushMatrix();
  translate(0, 50, 0);
  rotateX(radians(90));
  fill(100, 200, 100);
  rectMode(CENTER);
  rect(0, 0, 500, 500);
  popMatrix();

  // プレイヤー（動かすキューブ）
  pushMatrix();
  translate(playerX, playerY, playerZ);
  fill(200, 100, 100);
  box(50);
  popMatrix();
}

void keyPressed() {
  if (key == 'w') playerZ -= 10;
  if (key == 's') playerZ += 10;
  if (key == 'a') playerX -= 10;
  if (key == 'd') playerX += 10;
  if (key == ' ') playerY -= 10;     // ジャンプ
  if (keyCode == SHIFT) playerY += 10; // しゃがみ
}
##スクリーンショット

