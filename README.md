# Battlefield 1 — Annihilator (3D printable, two versions)

Fan-made 1:1 printable kit of the Annihilator from Battlefield 1. Overall length about **785 mm**. Everything prints on a **200 × 200 mm** bed, split into 9 body blocks plus a 2-section magazine.

Two versions share the same geometry and the same split layout — the only difference is the surface:

| Version | Surface |
| --- | --- |
| **Engraved** | Real relief baked into the mesh: scrollwork on the receiver side plates, magazine sides and the barrel band ring |
| **Classic** | Clean geometry, no relief — for people who want to paint, sand, or start from a plain base |

Blocks are interchangeable between the two versions: split positions and pin holes are identical.

## Download

Grab a zip from [Releases](../../releases):

- `annihilator engraved print kit.zip` — 9 body blocks, 2 magazine sections, 3 detachable-magazine parts, readme, previews
- `annihilator classic print kit.zip` — same layout, no engraving

The whole-gun meshes (260 MB each, unsplit) are **not** in the release: nobody prints a 785 mm part in one piece. Ask if you need them.

## Fixed magazine or detachable magazine

Each kit contains both. Print the 9 body blocks, then choose:

- **Fixed** — use `body x04 z01.stl` from `split/body 9pcs/` and `magazine seg 01/02 fixed.stl`. The magazine is a solid part that stays in place.
- **Detachable** — swap body block 4 for `body x04 z01 detachable.stl` (the magazine well, dimples and guide grooves are cut) and print `magazine seg 01/02 detachable.stl`.

The detachable magazine uses a U-slot in the upper magazine section to form a spring tongue with a symmetric bump on each side. The well wall has matching dimples and guide grooves.

- Clearance: 0.3 mm per side
- Seated: geometric interference 0
- First 4.5 mm of travel: the tongue flexes over the bumps
- After that: rigid slide, checked to 110 mm travel, no interference

**The detachable magazine is a geometry prototype and has not been test printed.** Snap force, fatigue life and real printer tolerance are unverified. Insert slowly the first time; if it is too tight, do not force it — thin the tongue or reduce the bump height.

## Print settings

- Layer height 0.16–0.20 mm, walls ≥ 3 perimeters
- Infill 20 % is enough (the whole magazine weighs about 105 g)
- PLA is fine. Use PETG for the magazine if it will be inserted and removed often
- The 0.6 mm decorative strip on the handguard needs **Arachne / variable line width** with a 0.4 mm nozzle, otherwise it will not print
- Add a **brim** to the blocks marked ⚠ below

## Orientation (least steep overhang per block)

| File | Facing down | Steep overhang | Bed contact | Height |
| --- | --- | --- | --- | --- |
| body x01 z01 | +X | 5.2 % | 1.4 % ⚠ | 136 mm |
| body x02 z01 | +Z | 0.1 % | 15.7 % | 105 mm |
| body x02 z02 | +X | 5.4 % | 2.4 % ⚠ | 136 mm |
| body x03 z01 | −X | 0.2 % | 27.2 % | 39 mm |
| body x03 z02 | +X | 3.6 % | 5.4 % | 136 mm |
| body x04 z01 | −X | 3.8 % | 7.5 % | 181 mm |
| body x05 z01 | +Z | 1.0 % | 9.7 % | 123 mm |
| body x05 z02 | −X | 1.9 % | 4.3 % | 136 mm |
| body x06 z01 | −X | 1.1 % | 8.3 % | 131 mm |
| seg 01 | +Z | 2.2 % | 6.6 % | 110 mm |
| seg 02 | −Z | 2.0 % | 6.4 % | 105 mm |

`body x04 z01` is the longest block at 181 mm because the bolt that used to bridge the cut now lives inside it. Facing −X down puts the bolt above the body, so it needs no extra support.

## Assembly

Six segments along the length, three of which are split again by height — 9 blocks in total. At every seam the left block carries the pin, the right block carries the hole.

Pins are **Φ4 × 5 mm**, 0.2 mm clearance per side. Pins locate the parts; you still need glue on the mating faces (CA or model glue).

| Seam (left \| right) | Position |
| --- | --- |
| body x01 z01 \| body x02 z02 | X = −262.3 |
| body x02 z01 \| body x02 z02 | Z = 116.8 |
| body x02 z01 \| body x03 z01 | X = −131.4 |
| body x02 z02 \| body x03 z02 | X = −131.4 |
| body x03 z01 \| body x03 z02 | Z = 117.5 |
| body x03 z02 \| body x04 z01 | X = −0.6 |
| body x04 z01 \| body x05 z01 | X = 130.3 |
| body x04 z01 \| body x05 z02 | X = 130.3 |
| body x05 z01 \| body x05 z02 | Z = 118.2 |
| body x05 z02 \| body x06 z01 | X = 261.2 |
| seg 01 \| seg 02 | Z = 91.8 (magazine) |

Numbering runs from the muzzle to the stock: `x01` is the muzzle end, `x06` the stock. `z01` is the lower half, `z02` the upper half.

Suggested order:

1. `x01_z01` → `x02_z02` (muzzle section and upper handguard)
2. `x02_z01` (lower foregrip)
3. `x03_z01` → `x03_z02`, then `x04_z01` (receiver)
4. `x05_z01` / `x05_z02` (grip and front of the stock), then `x06_z01` (stock)
5. Glue the two magazine sections separately, insert last

## Mesh verification

| Item | Engraved | Classic |
| --- | --- | --- |
| Body blocks / magazine sections | 9 / 2 | 9 / 2 |
| Watertight | yes | yes |
| Non-manifold / boundary edges | 0 / 0 | 0 / 0 |
| Max edge length | 181.1 mm | 180.1 mm |
| Sum of body block volume | 2,005,573 mm³ | 1,988,408 mm³ |
| Unsplit body volume | 2,005,899 mm³ | 1,988,714 mm³ |
| Difference (pin holes − seam fill) | 326 mm³ | 306 mm³ |
| Whole gun union volume | 2,343,270 mm³ | 2,323,969 mm³ |

The source model is a 2009-era game asset with only 6.3k faces, so the surfaces are smooth-shaded rather than finely detailed. The engraving was baked into geometry from a normal map, which is why it holds up at print scale but is not razor sharp.

## License and disclaimer

Fan art, **non-commercial only**. Battlefield 1 and the Annihilator design belong to DICE / EA. This is an unofficial fan model, not affiliated with or endorsed by them.

My own contribution (the mesh work, splitting, pins, detachable magazine design) is released under **CC BY-NC-SA 4.0** — share and remix with attribution, non-commercial, same license.

---

# 中文说明

《战地1》Annihilator 冲锋枪，1:1 可打印模型，整枪长约 785 mm，全部件都在 200 mm 打印床以内，枪身切 9 块、弹匣切 2 段。

两个版本几何完全同构，切法、销孔一致，块与块可以互换，唯一差别是表面：

- **雕花版**：机匣侧板、弹匣侧面、护木环带带真实浮雕（法线贴图烘成几何）
- **原版**：干净几何，无浮雕，适合自己上色或打磨

## 下载

到 [Releases](../../releases) 拿 zip：

- `annihilator engraved print kit.zip` — 雕花版，9 块枪身 + 2 段弹匣 + 3 件可拆弹匣件 + 说明
- `annihilator classic print kit.zip` — 原版，结构相同

整件（未切块，单个 260 MB）没放进 Release，没人整件打一把 785 mm 的枪。需要的话提 issue。

## 固定弹匣 / 可拆弹匣

两个包里都带。打完 9 块枪身之后二选一：

- **固定**：用 `split/body 9pcs/` 里的 `body x04 z01.stl`，配 `magazine seg 01/02 fixed.stl`
- **可拆**：第 4 块换成 `body x04 z01 detachable.stl`（掏了弹匣井、凹坑和导槽），弹匣用 `magazine seg 01/02 detachable.stl`

可拆弹匣靠上段 U 型槽形成弹性舌，舌尖带对称凸点，井壁有对应凹坑和导槽。单边间隙 0.3 mm；坐到底干涉为 0；抽出初段约 4.5 mm 是弹性舌弯曲越过凸点的行程，之后刚体滑动到 110 mm 无干涉。

**这是几何原型，没做过实物打样。** 卡扣力、疲劳寿命、实际打印误差都没验证。第一次慢慢插拔，太紧别硬掰，先减舌厚或降凸点。

## 打印参数

层高 0.16–0.20 mm，壁厚 ≥3 圈，填充 20% 足够（整只弹匣约 105 g）。PLA 就够，弹匣要频繁插拔建议 PETG。护木那条 0.6 mm 细装饰条必须开 Arachne（可变线宽），0.4 喷嘴否则打不出来。底面接触低于 5% 的块加 brim。

## 拼装

销 Φ4 × 5 mm，单边间隙 0.2 mm，销只负责对位，接缝照样要上胶。接缝位置、拼装顺序、每块的最佳摆放朝向都在英文部分的三张表里，对照文件名看即可。

## 授权

同人作品，**仅限非商用**。战地1 与 Annihilator 设计版权归 DICE / EA，本模型与其无隶属关系。我做的部分（网格处理、切块、销位、可拆弹匣设计）按 **CC BY-NC-SA 4.0** 发布：署名、非商用、同样方式共享。
