# zmk-config-lily58

无线 Lily58 分体键盘 ZMK 固件配置。

## 硬件清单

| 组件 | 型号 |
|------|------|
| 键盘 | Lily58 (58键分体) |
| 主控 | Nice!Nano v2 ×2 (nRF52840) |
| 连接 | 蓝牙 BLE 无线 |
| 电池 | 3.7V 110mAh ×2 |

## 仓库结构

```
├── .github/workflows/build.yml   # GitHub Actions 自动编译
├── build.yaml                     # 构建目标 (nice_nano_v2 ×2)
└── config/
    ├── lily58.conf                # 无线 + 省电配置
    └── lily58.keymap              # 键位映射 (双层 + 蓝牙切换)
```

## 编译固件

Push 触发 GitHub Actions 自动编译，在 Actions → Artifacts 下载 `.uf2` 文件。

## 刷写

1. Nice!Nano 连电脑，快速双击复位按钮
2. 弹出 `NICENANO` 盘符
3. 拖入对应的 `.uf2` 文件（左 `lily58_left` / 右 `lily58_right`）

## 键位

### Layer 0 — 默认 QWERTY

```
 ESC   1  2  3  4  5     6  7  8  9  0   -
 TAB   Q  W  E  R  T     Y  U  I  O  P  BSPC
CTRL   A  S  D  F  G     H  J  K  L  ;  RET
SFT    Z  X  C  V  B     N  M  ,  .  /  RSFT
         GUI ALT MO(1)   MO(1) ALT CTRL
```

### Layer 1 — 功能层 (按住拇指区触发)

```
  `    F1 F2 F3 F4 F5    F6 F7 F8 F9 F10 F11
 DEL                                ↑        F12
CTRL                          ←  ↓  →
SFT                                    RSFT
      清蓝牙 设备0             设备1 设备2
```

## 蓝牙切换

| 操作 | Layer 1 组合键 |
|------|---------------|
| 清除配对 | 左拇指 + Z |
| 电脑 (设备0) | 左拇指 + X |
| 设备1 (iPad) | 右拇指 + M |
| 设备2 | 右拇指 + , |
