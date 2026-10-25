<a id="top"></a><p align="right"><b>Tiếng Việt</b> · <a href="README.md">English</a></p>

<h1 align="center">PSArt + YourManager cho Photoshop</h1>

<p align="center">Hai panel Photoshop cho người vẽ: PSArt làm sạch, tách layer, vẽ lại nét; YourManager theo dõi mọi version PSD.</p>

<p align="center"><img src="docs/media/psart/hero.png" alt="Kết quả các công cụ PSArt: tách layer, nét vector, ảnh AI đã làm sạch, xoá nền, lưới phối cảnh, nét đã làm mượt" width="820"></p>

- **Tách** tranh thành layer trong vài giây
- **Chuyển** lineart ảnh thành nét vector sắc
- **Làm sạch** ảnh AI, xoá nền trơn
- **Tìm** file PSD gốc của bất kỳ ảnh đã xuất

<p align="center"><a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/PSArt_1.5.0.zip"><img alt="Tải PSArt 1.5.0" src="https://img.shields.io/badge/Tải-PSArt%201.5.0-2ea44f?style=for-the-badge"></a> <a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/YourManager_0.3.2.zip"><img alt="Tải YourManager 0.3.2" src="https://img.shields.io/badge/Tải-YourManager%200.3.2-1f6feb?style=for-the-badge"></a></p>

Chỉ Windows, Photoshop 2023 trở lên. Hình minh hoạ là kết quả thật của plugin trên ảnh thử.

## Cài đặt

### PSArt 1.5.0

Tải: **[PSArt_1.5.0.zip](https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/PSArt_1.5.0.zip)** · [Mọi phiên bản](https://github.com/DanhBoo/psart-plugin/releases)

1. Tắt Photoshop, xoá bản cũ trong `Plug-ins` ("PSArtCodex", "PSArt Codex" hoặc "PSArt").
2. Chuột phải file zip > Properties > tick **Unblock** > OK, rồi giải nén.
3. Chép thư mục `PSArt` vào `C:\Program Files\Adobe\Adobe Photoshop <năm>\Plug-ins\` (đúng là `Plug-ins\PSArt\manifest.json`).
4. Mở Photoshop > **Plugins** > **PSArt**. Hộp hỏi quyền `start_bridge.vbs` (chương trình nối của tab Codex): tick *Remember my choice* rồi bấm **Allow**; không dùng Codex thì bấm **Deny** cũng được.

Hướng dẫn cài đầy đủ: [CAI_DAT_PSArt.txt](CAI_DAT_PSArt.txt)

### YourManager 0.3.2

Tải: **[YourManager_0.3.2.zip](https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/YourManager_0.3.2.zip)** · [Mọi phiên bản](https://github.com/DanhBoo/psart-plugin/releases)

1. Tắt Photoshop; xoá bản YourManager cũ trong Plug-ins.
2. Chép thư mục `ptsplugin` trong zip vào `C:\Program Files\Adobe\Adobe Photoshop <năm>\Plug-ins\`.
3. Mở Photoshop > **Plugins** > **YourManager** (ngôn ngữ: **Settings > Language**).
4. Lần đầu Tìm / Xoá file, Photoshop hỏi chạy file .vbs: bấm **Allow**.

Hướng dẫn cài đầy đủ: [CAI_DAT_YourManager.txt](CAI_DAT_YourManager.txt)

## Yêu cầu hệ thống

**PSArt**

- Windows 10 / 11
- Photoshop 2023 (bản 24.2) trở lên
- Riêng tab Codex: Codex đã cài (app Codex hoặc `npm i -g @openai/codex`) và đăng nhập bằng tài khoản ChatGPT. Không cần Node.js.

**YourManager**

- Windows 10 / 11
- Photoshop 2023 (bản 24.0) trở lên

## Tính năng tóm tắt

| Công cụ | Tab | Làm gì |
|---|---|---|
| [Separate to New Layer](#psart-sepcard) | PSArt · Layer Tools | Khoanh một phần, nhấc lên layer riêng; chỗ trống phía sau được lấp. |
| [Extract Lines](#psart-linecard) | PSArt · Lineart | Biến lineart ảnh thành layer vector, phóng to vẫn sắc. |
| [Repair](#psart-repaircard) | PSArt · Lineart | Nối nét đứt và làm mượt nét run. |
| [Line weight **Beta**](#psart-weightcard) | PSArt · Lineart | Làm nét mảnh hơn hoặc dày hơn chỉ một cú bấm. |
| [Select](#psart-selectcard) | PSArt · Lineart | Khoanh thô; được vùng chọn ôm sát nét. |
| [Clean AI Image **Beta**](#psart-cleancard) | PSArt · Clean | Làm dịu nhiễu ảnh AI: nét một màu, mép mượt, màu sạch. |
| [Remove background](#psart-bgcard) | PSArt · Clean | Xoá nền trơn với mép mượt, kể cả khe hở. |
| [Smooth Color Lines **Beta**](#psart-cfixcard) | PSArt · Clean | Làm mượt nét trong tranh màu; màu giữ nguyên. |
| [Perspective Grid](#psart-gridcard) | PSArt · Perspective | Vẽ vài nét thô; được lưới phối cảnh đều. |
| [Redraw on grid](#psart-redrawcard) | PSArt · Perspective | Vẽ lại nét phác thẳng theo lưới, kèm vòng tròn đúng phối cảnh. |
| [Export & Replace](#psart-replacecard) | PSArt · Layer Tools | Xuất vùng chọn ra PNG, sửa ở đâu cũng được, thả về đúng khung cũ. |
| [Codex](#psart-codex) | PSArt · Codex | Chat với Codex ngay trong Photoshop; gửi vùng chọn, thả kết quả về. |
| [Dự án](#ym-projects) | YourManager · Dự án | Cứ lưu như thường; version mới tự nằm trên cùng dự án. |
| [ID nằm trong file](#ym-file_id) | YourManager · Dự án | Đổi tên, chép, dời PSD; file vẫn nhớ dự án và version. |
| [Tìm PSD / PSB dự án từ ảnh / PSD](#ym-find) | YourManager · Tìm | Thả ảnh JPG / PNG đã xuất; ra PSD gốc và version mới nhất. |
| [Lịch sử thao tác](#ym-history) | YourManager · Lịch sử | Đổi ý? Bấm một bước để quay về. |
| [Cài đặt](#ym-settings) | YourManager · Cài đặt | Chọn quét gì, ngôn ngữ, làm mới dữ liệu. |
| [Hỏi khi lưu version cũ](#ym-save_ask) | YourManager · Cài đặt | Lưu version cũ? Một cú bấm đưa lên trên cùng. |

<a id="psart"></a>

## PSArt 1.5.0

**Một panel Photoshop: tách layer, lineart vector, làm sạch ảnh AI, lưới phối cảnh, chat Codex.**

Công cụ nặng chạy ngầm. Rê chuột lên nút nào là có ô Help ngắn.

<a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/PSArt_1.5.0.zip"><img alt="Tải PSArt 1.5.0" src="https://img.shields.io/badge/Tải-PSArt%201.5.0-2ea44f?style=for-the-badge"></a>

### Layer Tools

Tách một phần layer ra layer riêng, xuất ảnh đi sửa rồi thay lại vào file.

<p align="center"><img src="docs/media/psart/panel_layers.png" alt="Tab Layer Tools" width="300"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="psart-sepcard"></a>

#### Separate to New Layer

*Khoanh một phần, nhấc lên layer riêng; chỗ trống phía sau được lấp.*

<p align="center"><img src="docs/media/psart/sepRun.gif" alt="Nhân vật được khoanh thành layer riêng, chỗ trống để lại được lấp bằng màu nền xung quanh" width="720"></p>

**Cách dùng**

1. Chọn tranh ở **Layer**.
2. Khoanh phần cần tách.
3. Bấm **Separate to New Layer**.

<details><summary>Mẹo & giới hạn</summary>

- Chỗ lấp là pha màu xung quanh; vùng ẩn lớn thì vẽ tay thêm.

</details>

### Lineart

Vẽ lại nét raster thành layer vector, nối / làm mượt nét, đổi độ dày nét, chọn vùng giữa các nét.

<p align="center"><img src="docs/media/psart/panel_lineart.png" alt="Tab Lineart" width="300"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="psart-linecard"></a>

#### Extract Lines

*Biến lineart ảnh thành layer vector, phóng to vẫn sắc.*

<p align="center"><img src="docs/media/psart/lineRun.gif" alt="Nét bể pixel khi phóng 4 lần trở thành nét vector mượt" width="720"></p>

**Cách dùng**

1. Chọn layer nét ở **Lineart**.
2. Chỉnh **Options** nếu cần.
3. Bấm **Extract Lines**.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **Close gaps** - Nối luôn các chỗ đứt nhỏ trên nét.
- **Auto colors** - Lấy màu từ chính lineart; tắt thì dùng 4 ô màu (core, faint, body, edge).

**Mẹo & giới hạn**

- Xong thì bấm Done trên thanh để chọn các layer mới.

</details>

<a id="psart-repaircard"></a>

#### Repair

*Nối nét đứt và làm mượt nét run.*

<p align="center"><img src="docs/media/psart/fixRun.gif" alt="Smooth Lines, phóng to: nét run, dày mỏng không đều thành nét mượt, đều" width="720"></p>

<p align="center"><img src="docs/media/psart/joinRun.gif" alt="Join line nối chỗ đứt trên nét" width="720"></p>

**Cách dùng**

1. Chọn layer nét.
2. Khoanh chỗ đứt hoặc chỗ run.
3. Bấm **Join line** hoặc **Smooth Lines**.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **Keep corners** - Góc gắt giữ nguyên; tắt thì bo tròn.
- **Strength** - 0 chỉ làm mượt; cao hơn vẽ lại nét sạch hơn; trên 20 đường cong đơn giản và đều hơn.

**Mẹo & giới hạn**

- Join line cần đúng hai đầu nét trong vùng chọn.

</details>

<a id="psart-weightcard"></a>

#### Line weight <sup><b>Beta</b></sup>

*Làm nét mảnh hơn hoặc dày hơn chỉ một cú bấm.*

**Cách dùng**

1. Chọn layer nét.
2. Chọn **Step**.
3. Bấm **Thinner** hoặc **Thicker**.

<a id="psart-selectcard"></a>

#### Select

*Khoanh thô; được vùng chọn ôm sát nét.*

<p align="center"><img src="docs/media/psart/fillSelect.gif" alt="Vòng khoanh ẩu trên một phần vùng được nới ra tới các nét bao quanh" width="720"></p>

**Cách dùng**

1. Chọn lineart ở Extract Lines.
2. Khoanh qua các vùng.
3. Bấm **Select**, rồi tô.

<details><summary>Tuỳ chọn</summary>

- **Reach** - Vòng khoanh lấy tới đâu. Tight: chỉ phần được phủ. Wide: cả vùng, như Magic Wand.

</details>

### Clean

Làm sạch ảnh AI, xoá nền trơn, làm mượt nét trên tranh màu.

<p align="center"><img src="docs/media/psart/panel_clean.png" alt="Tab Clean" width="300"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="psart-cleancard"></a>

#### Clean AI Image <sup><b>Beta</b></sup>

*Làm dịu nhiễu ảnh AI: nét một màu, mép mượt, màu sạch.*

<p align="center"><img src="docs/media/psart/cleanRun.gif" alt="Trước và sau Clean trên một khuôn mặt ảnh AI" width="720"></p>

**Cách dùng**

1. Chọn layer ảnh AI.
2. Chỉnh màu nét nếu cần.
3. Bấm **Clean**.

<a id="psart-bgcard"></a>

#### Remove background

*Xoá nền trơn với mép mượt, kể cả khe hở.*

<p align="center"><img src="docs/media/psart/bgRun.gif" alt="Nền xám quanh quầy hàng biến thành trong suốt" width="720"></p>

**Cách dùng**

1. Chọn layer ảnh.
2. Để **Background** ở Auto.
3. Bấm **Remove**.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **Remove enclosed gaps** - Xoá cả phần nền lọt qua các khe kín.
- **Smooth** - 0 giữ mép như cũ; cao hơn thì mượt hơn; 2-3 bo cả góc.

**Mẹo & giới hạn**

- Không dùng cho nền ảnh chụp phức tạp.
- Chủ thể chạm mép ảnh thì chọn Light hoặc Dark.

</details>

<a id="psart-cfixcard"></a>

#### Smooth Color Lines <sup><b>Beta</b></sup>

*Làm mượt nét trong tranh màu; màu giữ nguyên.*

**Cách dùng**

1. Chọn tranh; khoanh các nét.
2. Chỉnh **Strength**.
3. Bấm **Smooth**.

### Perspective

Dựng lưới phối cảnh từ vài nét nháp và vẽ lại bản phác theo lưới.

<p align="center"><img src="docs/media/psart/panel_persp.png" alt="Tab Perspective" width="300"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="psart-gridcard"></a>

#### Perspective Grid

*Vẽ vài nét thô; được lưới phối cảnh đều.*

<p align="center"><img src="docs/media/psart/perspMake.gif" alt="Năm nét nháp thành một rẻ quạt đường lưới" width="720"></p>

**Cách dùng**

1. Vẽ vài nét thô trên layer mới.
2. Chọn **Type** và **Density**.
3. Bấm **Make grid**.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **Density** - Số đường lưới; đổi là vẽ lại các layer lưới đang chọn trong bảng Layers.

**Mẹo & giới hạn**

- Chạy Curved hai lần, ngang và dọc, để có cong 4 điểm.

</details>

<a id="psart-redrawcard"></a>

#### Redraw on grid

*Vẽ lại nét phác thẳng theo lưới, kèm vòng tròn đúng phối cảnh.*

<p align="center"><img src="docs/media/psart/perspCircle.gif" alt="Vòng tròn phác run thành elip phối cảnh sạch" width="720"></p>

**Cách dùng**

1. Thêm và tick lưới (**+ Grid**).
2. Khoanh phần phác.
3. Bấm **Straighten** hoặc **Perspective Circle**.

### Sửa 1 phần tranh bằng AI

<a id="psart-replacecard"></a>

#### Export & Replace

*Xuất vùng chọn ra PNG, sửa ở đâu cũng được, thả về đúng khung cũ.*

**Cách dùng**

1. Chọn **Export folder** (nút bánh răng).
2. Bấm **Export**.
3. Sửa PNG, chọn lại ở ô, bấm **Replace**.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **All visible layers** - Xuất một ảnh gộp mọi layer đang hiện, không chỉ layer đang chọn.
- **Transparent / Background** - Giữ vùng trống trong suốt, hoặc tô bằng màu Background.
- **Stretch to fit** - Kéo giãn ảnh cho khít khung; tắt thì giữ tỉ lệ.

**Mẹo & giới hạn**

- Hợp để sửa bằng AI: kết quả về khớp từng điểm ảnh.

</details>

<a id="psart-codex"></a>

#### Codex

*Chat với Codex ngay trong Photoshop; gửi vùng chọn, thả kết quả về.*

**Cách dùng**

1. Bấm **Connect**.
2. Chọn vùng, gõ tin nhắn.
3. Bấm **Send**; chuột phải ảnh > **Replace**.

<details><summary>Mẹo & giới hạn</summary>

- Cần app Codex đăng nhập tài khoản ChatGPT; các tab khác không cần.

</details>

<p align="center"><img src="docs/media/psart/panel_codex.png" alt="Tab Codex" width="300"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<p align="right"><a href="#top">lên đầu trang</a></p>

<a id="ym"></a>

## YourManager 0.3.2

**Mọi version PSD trong một list theo dự án, đổi tên, chép hay dời file vẫn nhận ra.**

Mã dự án nhỏ được lưu trong mỗi PSD, nên đổi tên hay dời file panel vẫn nhận ra. Mọi thứ chỉ chạy trên máy bạn.

<a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.25/YourManager_0.3.2.zip"><img alt="Tải YourManager 0.3.2" src="https://img.shields.io/badge/Tải-YourManager%200.3.2-2ea44f?style=for-the-badge"></a>

### Dự án

<p align="center"><img src="docs/media/ym/panel_projects_vi.png" alt="Tab Dự án: bốn dự án mẫu, Character đang xổ với version v1 tới v4" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="ym-projects"></a>

#### Dự án

*Cứ lưu như thường; version mới tự nằm trên cùng dự án.*

<p align="center"><img src="docs/media/ym/versions_on_save_vi.gif" alt="Save As character_v05.psd: v5 hiện trên cùng dự án Character" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

**Cách dùng**

1. Mở PSD và lưu.
2. Mỗi version mới thì Save As tên mới.
3. Ở **Dự án**, nhấp đúp một version để mở.

<details><summary>Tuỳ chọn / Mẹo & giới hạn</summary>

**Tuỳ chọn**

- **Chuột phải một version** - Mở, mở thư mục, đổi tên, dời, xoá (vào Thùng rác).

**Mẹo & giới hạn**

- Đổi tên / dời file đang mở: plugin lưu, đóng rồi mở lại.

</details>

<a id="ym-file_id"></a>

#### ID nằm trong file

*Đổi tên, chép, dời PSD; file vẫn nhớ dự án và version.*

<p align="center"><img src="docs/media/ym/rename_keeps_id_vi.gif" alt="Đổi tên character_v02.psd trong Explorer rồi mở: dòng thành character_lineart.psd, vẫn v2" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

**Cách dùng**

1. Đổi tên hoặc dời PSD trong Explorer.
2. Mở nó trong Photoshop.
3. Dòng của nó ở **Dự án** đổi theo.

### Tìm

<p align="center"><img src="docs/media/ym/panel_find_vi.png" alt="Tab Tìm sau khi thả một ảnh JPG đã xuất: ba file PSD khớp" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="ym-find"></a>

#### Tìm PSD / PSB dự án từ ảnh / PSD

*Thả ảnh JPG / PNG đã xuất; ra PSD gốc và version mới nhất.*

<p align="center"><img src="docs/media/ym/find_from_image_vi.gif" alt="Thả character_export.jpg vào Tìm: ra ba file PSD, bấm Mở nhảy tới character_v03.psd ở tab Dự án" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

**Cách dùng**

1. Bấm **Quét ID PSD / PSB / ảnh** một lần.
2. Thả ảnh hoặc PSD vào ô.
3. Bấm **Mở** ở một kết quả.

<details><summary>Mẹo & giới hạn</summary>

- Chuẩn nhất với ảnh xuất từ Photoshop.

</details>

### Lịch sử

<p align="center"><img src="docs/media/ym/panel_history_vi.png" alt="Tab Lịch sử với ba thao tác, thao tác cuối đã hoàn tác" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="ym-history"></a>

#### Lịch sử thao tác

*Đổi ý? Bấm một bước để quay về.*

**Cách dùng**

1. Mở **Lịch sử**.
2. Bấm một dòng để quay về.
3. Bấm dòng mờ để làm lại.

### Cài đặt

<p align="center"><img src="docs/media/ym/panel_settings_vi.png" alt="Tab Cài đặt, mở cả bốn mục" width="360"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

<a id="ym-settings"></a>

#### Cài đặt

*Chọn quét gì, ngôn ngữ, làm mới dữ liệu.*

**Cách dùng**

1. Mở **Cài đặt**.
2. Thêm thư mục quét; chọn loại file.
3. Chọn ngôn ngữ.

<details><summary>Mẹo & giới hạn</summary>

- Xoá `%APPDATA%\YourManager` để gỡ sạch.

</details>

<a id="ym-save_ask"></a>

#### Hỏi khi lưu version cũ

*Lưu version cũ? Một cú bấm đưa lên trên cùng.*

<p align="center"><img src="docs/media/ym/ask_on_save_vi.png" alt="Hộp hỏi: Đây có phải version mới nhất? - Không / Có, đưa lên trên cùng" width="400"></p>

<p align="center"><sub>ảnh dựng, không phải ảnh chụp Photoshop</sub></p>

**Cách dùng**

1. Lưu một version không nằm trên cùng.
2. Bấm **Có, đưa lên trên cùng** hoặc **Không**.

<details><summary>Mẹo & giới hạn</summary>

- Bật lại câu hỏi ở **Cài đặt > Thông báo**.

</details>

<p align="right"><a href="#top">lên đầu trang</a></p>

## Có gì mới

### PSArt 1.5.0

- Công cụ nặng chạy ngầm, mỗi việc một thanh.

- Bố cục mới: tab icon, mỗi công cụ một khung, ô Help dưới chuột.

  <img src="docs/media/psart/panel_lineart.png" alt="Tab Lineart" width="480">

- Tên dễ hiểu hơn; Select chuyển sang tab Lineart. ([→](#psart-selectcard))

- Tab Codex dùng như trang chat. ([→](#psart-codex))

### YourManager 0.3.2

- Tìm không cần Python nữa. ([→](#ym-find))

- **Không thuộc dự án này** chuyển file sang dự án mới. ([→](#ym-projects))

- Kết quả tìm gọn hơn: **Sát với hình** và **Mới nhất**. ([→](#ym-find))

## Hỏi đáp

<details><summary><b>Có chạy trên macOS không?</b></summary>

Chưa. Cả hai plugin mới chỉ được làm và thử trên Windows.
</details>

<details><summary><b>Tranh của tôi có bị gửi đi đâu không?</b></summary>

Các công cụ vẽ của PSArt và YourManager chỉ chạy trên máy bạn. Chỉ tab Codex của PSArt gửi dữ liệu ra ngoài: tin nhắn và vùng chọn bạn bấm gửi, tới Codex bằng tài khoản ChatGPT của chính bạn.
</details>

<details><summary><b>Bị lỗi thì gửi gì?</b></summary>

Dòng chữ ở cuối panel, phiên bản Photoshop và bạn vừa bấm gì.
</details>

<details><summary><b>PSArt hỏi quyền chạy start_bridge.vbs, có cần không?</b></summary>

Chỉ tab Codex cần. Không dùng Codex thì bấm Deny, các tab khác vẫn chạy bình thường.
</details>

<details><summary><b>YourManager có sửa file PSD của tôi không?</b></summary>

Nó chỉ thêm một mã dự án nhỏ vào phần thông tin file (XMP) lúc bạn lưu. Layer và điểm ảnh không bị đụng tới.
</details>

## Liên hệ
Đây là bản thử cho bạn bè. Báo lỗi hay góp ý ở [Issues](https://github.com/DanhBoo/psart-plugin/issues) hoặc nhắn trực tiếp cho tác giả.
