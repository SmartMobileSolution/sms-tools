# TÀI LIỆU BÀN GIAO WEBSITE — SMART MOBILE SOLUTION (SMS)

**Cập nhật lần cuối:** 23/11/2026  
**Repository:** `SmartMobileSolution/sms-tools`  
**Branch:** `main`  
**Website:** https://smartmobilesolution.github.io/sms-tools/

> Tài liệu này chỉ bàn giao những công việc đã thực hiện trong phạm vi xây dựng và cập nhật website Smart Mobile Solution. Không phải tài liệu bàn giao source code ứng dụng Android Kids Safe.

## 1. Mục tiêu và phạm vi website

Website là trang giới thiệu Smart Mobile Solution (SMS), danh sách ứng dụng, thông tin liên hệ và các trang Privacy Policy tương ứng với từng ứng dụng. Website hiện được tổ chức theo dạng static website với HTML, CSS và JavaScript; không ghi nhận framework frontend hoặc quy trình build riêng trong các file đã xử lý.

## 2. Công việc đã thực hiện

- Xây dựng/chỉnh sửa trang chủ giới thiệu Smart Mobile Solution, thông điệp thương hiệu, khu vực Our Apps và các liên kết điều hướng.
- Xây dựng/chỉnh sửa trang danh sách ứng dụng tại `/apps/`, hiện có **Kids Safe: Parent Control** và **App Locker: Lock Apps**.
- Tạo trang giới thiệu App Locker tại `/apps/app-locker/`.
- Tạo Privacy Directory tại `/privacy/` và Privacy Policy tiếng Anh riêng cho App Locker tại `/privacy/app-locker/`.
- Xây dựng/chỉnh sửa trang Contact với email hỗ trợ `help.mobilesolution@gmail.com`.
- Soạn và cập nhật Privacy Policy cho Kids Safe: Parent Control bằng tiếng Anh và tiếng Việt.
- Tinh chỉnh giao diện dùng chung trong stylesheet: màu sắc xanh/teal, typography, card, navigation, trang policy và responsive cho màn hình nhỏ.
- Thay tham chiếu logo công ty từ `company-logo.svg` sang `company-logo.png` trên các trang HTML. Người dùng đã tự commit ảnh PNG gốc và xóa SVG cũ; phần code đã được cập nhật để trỏ đến PNG.
- Thay icon minh họa chữ K trên thẻ ứng dụng bằng ảnh tại `assets/images/kids-safe-icon.svg`.
- Đồng bộ Kids Safe card trên cả Home và Apps Directory: category `ANDROID · PARENTAL CONTROLS`, mô tả, tags `Kids Mode` / `Allowed apps` / `Parent PIN`, CTA Google Play và Privacy Policy, status `ANDROID`.
- Hoàn thiện App Locker detail page: gallery 5 ảnh đã được chuyển sang WebP tối ưu, responsive layout và lazy loading; bỏ link Privacy Policy dư ngay dưới nhóm CTA Hero.
- Chỉnh App Locker hero icon: hiển thị trực tiếp icon, không có khung/card/nền/glow trang trí bên ngoài.
- Xác minh GitHub Pages workflow #48 đã hoàn tất thành công cho commit `041a961de459a9656411134bcd18fe6aa7555a14` ngày 18/11/2026.

## 3. Repository và cấu trúc file hiện tại

| Đường dẫn | Vai trò |
|---|---|
| `index.html` | Trang chủ |
| `apps/index.html` | Danh sách ứng dụng |
| `apps/app-locker/index.html` | Trang giới thiệu App Locker: Lock Apps |
| `privacy/index.html` | Danh mục Privacy Policy theo ứng dụng |
| `privacy/app-locker/index.html` | Privacy Policy — App Locker (English) |
| `contact/index.html` | Trang liên hệ |
| `privacy/kids-safe/index.html` | Privacy Policy — English |
| `privacy/kids-safe/vi/index.html` | Privacy Policy — Tiếng Việt |
| `assets/css/styles.css` | Stylesheet dùng chung, responsive |
| `assets/js/site.js` | JavaScript dùng chung; hiện được gọi ở cuối các trang để hỗ trợ tiện ích website như năm ở footer |
| `assets/images/company-logo.png` | Logo công ty dạng PNG do người dùng upload/commit; HTML hiện trỏ đến file này |
| `assets/images/kids-safe-icon.svg` | Icon Kids Safe đang được Home, Apps và Privacy Directory tham chiếu |
| `assets/images/app-locker-icon.webp` | Icon App Locker dùng trên Home, Apps, Detail và Privacy Policy |
| `assets/images/app-locker/screenshots/screen-01.webp` … `screen-05.webp` | Năm ảnh WebP tối ưu đang được App Locker detail page sử dụng |

### Các URL hiện có

- Home: https://smartmobilesolution.github.io/sms-tools/
- Apps: https://smartmobilesolution.github.io/sms-tools/apps/
- App Locker Detail: https://smartmobilesolution.github.io/sms-tools/apps/app-locker/
- Privacy Directory: https://smartmobilesolution.github.io/sms-tools/privacy/
- App Locker Privacy EN: https://smartmobilesolution.github.io/sms-tools/privacy/app-locker/
- Contact: https://smartmobilesolution.github.io/sms-tools/contact/
- Privacy EN: https://smartmobilesolution.github.io/sms-tools/privacy/kids-safe/
- Privacy VI: https://smartmobilesolution.github.io/sms-tools/privacy/kids-safe/vi/

## 4. Thương hiệu và quy tắc tài nguyên ảnh

- Tên thương hiệu hiển thị: **Smart Mobile Solution (SMS)**.
- Logo dùng class `.brand-logo`; hiện các trang dùng `company-logo.png` cho cả logo trên header và favicon.
- Kích thước hiển thị logo được điều khiển trong `assets/css/styles.css`; không sửa file ảnh gốc để làm vừa giao diện. Dùng CSS `object-fit: contain` và giới hạn kích thước hiển thị.
- Icon ứng dụng dùng class `.app-icon`; ảnh hiện được tham chiếu từ `assets/images/kids-safe-icon.svg` trên Home và Apps.
- Người dùng đã nhấn mạnh ảnh logo phải dùng đúng file gốc, không tự ý chỉnh màu, crop, chuyển định dạng hoặc nén lại. Nếu cần thay asset, ưu tiên sử dụng nguyên file người dùng cung cấp và chỉ đổi đường dẫn trong HTML/CSS.
- Trước khi đổi tên hoặc xóa ảnh, tìm toàn bộ tham chiếu `src`, `href`, CSS `url(...)` và favicon trong repository.

**Lưu ý kỹ thuật:** icon Kids Safe trong trạng thái bàn giao đang được tham chiếu dưới phần mở rộng `.svg`; file này được tạo trong lần thay ảnh trước bằng cách bọc nội dung ảnh raster trong SVG. Không được mặc định đây là PNG gốc. Khi tiếp tục chỉnh sửa, agent cần kiểm tra file thực tế và xác nhận với người dùng trước khi thay nếu không có yêu cầu rõ ràng.

## 5. Nội dung Privacy Policy Kids Safe đã được công bố trên website

Cả hai bản EN/VI được giữ cấu trúc tương đương và phản ánh các thông tin do người dùng cung cấp:

- Kids Safe là công cụ dành cho cha mẹ, chạy trên chính điện thoại Android của cha mẹ khi trẻ mượn máy; không có tài khoản trẻ em, cloud family pairing hoặc điều khiển từ xa thiết bị riêng của trẻ ở phạm vi V1.
- Ứng dụng đọc thông tin ứng dụng đã cài đặt để cha mẹ chọn danh sách cho phép; trong Kids Mode đang hoạt động, kiểm tra app foreground để áp dụng giới hạn; không lưu lịch sử ứng dụng đã mở.
- Các thiết lập cần cho Kids Mode được lưu cục bộ; Parent PIN được mã hóa trước khi lưu. Trạng thái phiên và dữ liệu phiên liên quan được xóa khi phiên kết thúc.
- Firebase Analytics và Firebase Crashlytics dùng theo hành vi mặc định của SDK; không bổ sung custom events, user ID, custom user properties, Crashlytics custom keys hoặc custom logs.
- Firebase Remote Config dùng để bật/tắt định dạng quảng cáo và kiểm soát vị trí đặt quảng cáo; không dùng để cấu hình tần suất/thời điểm quảng cáo.
- Google AdMob dùng các định dạng Banner, Interstitial, App Open và Native. Ứng dụng được cấu hình yêu cầu quảng cáo không cá nhân hóa. SDK vẫn có thể xử lý thông tin kỹ thuật/quảng cáo cần thiết theo chính sách Google.
- Quảng cáo tắt khi Kids Mode đang hoạt động và khi người dùng có Premium đang hiệu lực.
- Google UMP đã được người dùng xác nhận là hoàn thiện popup/message xin consent và ghi nhận lựa chọn quyền riêng tư.
- Premium theo tháng/năm xử lý qua Google Play Billing; SMS không có payment server riêng và không upload giao dịch lên server riêng hoặc Firebase.
- Email hỗ trợ: `help.mobilesolution@gmail.com`; website: https://smartmobilesolution.github.io/sms-tools/.
- Ngày hiệu lực và cập nhật cuối cùng được người dùng yêu cầu giữ là **20 February 2022 / 20/02/2022**. Không tự ý thay ngày này nếu chưa được yêu cầu.

Privacy Policy là nội dung công bố theo thông tin từ người dùng, không phải ý kiến pháp lý hoặc xác nhận rằng app đã đáp ứng toàn bộ yêu cầu của Google Play hay luật tại mọi thị trường. Không tự suy diễn thêm loại dữ liệu hoặc hành vi xử lý chưa được xác nhận.

## 6. Quy tắc bắt buộc khi mở rộng website

Website cần được duy trì theo hướng dễ thêm ứng dụng mới mà không phải viết lại cấu trúc hoặc tạo các trang rời rạc thiếu nhất quán.

### 6.1 Danh sách ứng dụng

- Mỗi ứng dụng có một `slug` ổn định, viết thường, dùng dấu gạch ngang; ví dụ `kids-safe`.
- Thông tin card nên theo một cấu trúc thống nhất: tên app, icon, nền tảng, mô tả ngắn, tags, URL trang app và URL Privacy Policy.
- Khi số lượng ứng dụng tăng, ưu tiên quản lý metadata ở một nguồn dữ liệu trung tâm (ví dụ `assets/data/apps.json`) và render danh sách từ dữ liệu đó, thay vì sao chép một card HTML ở nhiều nơi.
- Giữ trang `/apps/` là danh mục tổng; không hard-code nội dung từng ứng dụng vào nhiều trang khác nhau nếu có thể dùng chung metadata.

### 6.2 Trang chi tiết cho từng ứng dụng

Đề xuất quy ước URL:

- `apps/<app-slug>/` — trang giới thiệu/landing page của ứng dụng.
- `privacy/<app-slug>/` — Privacy Policy tiếng Anh mặc định.
- `privacy/<app-slug>/vi/` — Privacy Policy tiếng Việt.

Ví dụ với app hiện có:

- `apps/kids-safe/`
- `privacy/kids-safe/`
- `privacy/kids-safe/vi/`

Không nhất thiết tạo lại trang chi tiết Kids Safe nếu chưa có yêu cầu; đây là quy ước mở rộng cho các app được thêm sau.

### 6.3 Template và tính nhất quán

- Giữ chung header, navigation, footer, typography, spacing, màu sắc, card, nút và responsive behavior giữa các trang.
- Tạo template hoặc component/partial dùng chung cho app detail page và privacy page khi bắt đầu có nhiều ứng dụng. Vì website hiện là static HTML, nếu thêm cơ chế include/build thì phải giải thích rõ, giữ GitHub Pages deployment hoạt động và tránh đưa framework lớn không cần thiết.
- Trang Privacy Policy của từng app cần có EN/VI đồng bộ nội dung, liên kết chuyển ngôn ngữ, thông tin app/developer và liên kết liên quan.
- Dùng relative paths chính xác theo độ sâu thư mục; kiểm tra logo, CSS, JS, favicon, app icon và các liên kết từ tất cả page depth.
- Không tạo các nội dung pháp lý theo kiểu copy nguyên policy Kids Safe cho app khác; phải hỏi/thu thập đúng hành vi và SDK của ứng dụng mới.

### 6.4 Quy trình thay đổi

1. Đọc source hiện tại trên branch `main` trước khi chỉnh sửa; không dựa hoàn toàn vào ghi chú bàn giao vì repository có thể đã thay đổi.
2. Xác định mọi trang và asset đang tham chiếu đến file cần đổi.
3. Giữ nguyên thiết kế và nội dung không liên quan đến yêu cầu.
4. Kiểm tra URL, relative paths, file ảnh, favicon, responsive layout và liên kết EN/VI.
5. Kiểm tra diff trước khi commit; không xóa asset cũ nếu chưa xác nhận không còn tham chiếu.
6. Commit với message mô tả rõ thay đổi; báo lại các file đã sửa và URL cần kiểm tra.

## 7. Các điểm agent tiếp nhận cần xác minh trước khi thay đổi

- Kiểm tra `assets/images/company-logo.png` đã tồn tại trên nhánh hiện tại và được tải được; không khôi phục tham chiếu `.svg` cũ.
- Kiểm tra `assets/images/kids-safe-icon.svg` và icon được hiển thị thế nào trên Home/Apps; không tự thay đổi asset nếu người dùng chưa yêu cầu.
- Kiểm tra các favicon/brand references trong cả 5 HTML pages đã liệt kê.
- Kiểm tra live website sau khi GitHub Pages deploy xong; không chỉ dựa vào trạng thái commit.
- Giữ ngày policy 20/02/2022 như yêu cầu trừ khi người dùng thay đổi.

## 8. Prompt khởi tạo agent tiếp nhận

Sao chép prompt sau và gửi kèm file bàn giao này trong cuộc trò chuyện mới:

> Bạn là agent tiếp nhận và phát triển tiếp website Smart Mobile Solution (SMS). Hãy đọc toàn bộ tài liệu bàn giao đính kèm trước khi làm việc. Repository là `SmartMobileSolution/sms-tools`, branch `main`, website https://smartmobilesolution.github.io/sms-tools/.
>
> Phạm vi của bạn chỉ là website này, không phải source code ứng dụng Android. Trước mọi thay đổi, hãy kiểm tra repository hiện tại vì code có thể đã thay đổi sau thời điểm lập tài liệu. Giữ nguyên thiết kế, nội dung và chức năng không liên quan đến yêu cầu.
>
> Yêu cầu kiến trúc quan trọng: mọi cập nhật phải hỗ trợ mở rộng danh sách ứng dụng, thêm landing/detail page riêng cho từng ứng dụng và thêm Privacy Policy EN/VI cho từng ứng dụng mới. Hãy dùng slug nhất quán, metadata tập trung khi phù hợp, template hoặc cấu trúc dùng chung, navigation/asset paths chính xác và responsive UI. Không tạo cấu trúc quá phức tạp hoặc thêm framework nếu chưa cần.
>
> Đối với logo, sử dụng `assets/images/company-logo.png` là ảnh gốc do người dùng cung cấp; không chuyển đổi, crop, nén, tô màu hoặc thay bằng SVG. Hãy tìm và kiểm tra toàn bộ tham chiếu trước khi sửa. Không tự ý thay icon app nếu không được yêu cầu.
>
> Khi chỉnh sửa Privacy Policy, chỉ sử dụng các thông tin đã được người dùng xác nhận và giữ nội dung EN/VI tương đương. Không suy diễn về dữ liệu, SDK, consent hoặc tuân thủ pháp lý. Ngày policy hiện được yêu cầu giữ là 20 February 2022.
>
> Với mỗi yêu cầu: (1) kiểm tra source và asset liên quan; (2) đề xuất kế hoạch ngắn nếu thay đổi nhiều file; (3) chỉnh sửa tối thiểu; (4) kiểm tra relative links, ảnh, favicon, responsive và các trang ngôn ngữ; (5) kiểm tra diff; (6) người dùng đã cấp quyền làm việc trực tiếp trên repository, được chỉnh sửa và commit/push lên `main` khi giao nhiệm vụ; (7) tuyệt đối không tự ý merge hoặc thay đổi cấu hình repository; (8) báo cáo rõ file, URL và các điểm còn chưa xác minh. Không tuyên bố đã kiểm tra live site nếu chưa thực sự kiểm tra.

## 9. Cách bàn giao cho agent mới

1. Tải file DOCX hoặc Markdown này về máy.
2. Mở một cuộc trò chuyện mới với agent muốn bàn giao. Nếu agent làm việc trực tiếp trên GitHub, kết nối/cấp quyền truy cập repository `SmartMobileSolution/sms-tools` trước.
3. Đính kèm file bàn giao vào cuộc trò chuyện mới.
4. Dán prompt ở Mục 8. Nêu thêm yêu cầu cụ thể đầu tiên bạn muốn agent xử lý.
5. Yêu cầu agent xác nhận đã đọc tài liệu, kiểm tra repository/branch hiện tại và tóm tắt trạng thái thật trước khi thực hiện thay đổi.
6. Với agent chạy local, yêu cầu clone repository, checkout `main`, kiểm tra source và commit gần nhất trước khi code. Không gửi token, mật khẩu hoặc thông tin bí mật trong prompt.

## 10. App Locker: Lock Apps — current website status

- App Locker is listed on Home and Apps.
- Its detail page is `/apps/app-locker/`.
- Its English Privacy Policy is `/privacy/app-locker/`; no Vietnamese version has been supplied or created.
- Owner decision (23/11/2026): an App Locker Vietnamese Privacy Policy is **not required**. Keep the English policy as the only App Locker policy language unless the owner changes this decision.
- Premium benefits shown on the detail page are: ad removal, unlimited app locking, and unlimited photo/video protection. Do not add unconfirmed technical claims such as biometric unlocking or uninstall protection.
- App icon: `assets/images/app-locker-icon.webp`. This is the active website asset, referenced by Home, Apps, the detail page and the Privacy Policy. The current tracked repository tree contains the WebP asset; do not assume the original supplied PNG is also stored in the repository.
- The hero icon is displayed directly, without an outer card/frame, decorative background, circular rings or glow. Its size is controlled by `assets/css/styles.css`.
- Google Play URL supplied by the user: `https://play.google.com/store/apps/details?id=org.app.secure.locker` (package `org.app.secure.locker`).
- Five owner-provided promotional screenshots are stored as original PNG files at `assets/images/app-locker/screenshots/screen-01.png` through `screen-05.png`. The gallery is part of the detail page, placed after the hero and before the features section. It uses lazy loading and responsive columns: five on wide desktop, three on medium/tablet widths, and two on mobile (the fifth card is centered).
- The five original PNGs total 10,571,304 bytes (about 10.57 MB decimal). Keep these originals unchanged. Add optimized WebP derivatives and update the gallery to use them once conversion is completed and visually validated.
- The detail page's Hero contains the Google Play CTA and Explore features CTA. The redundant Privacy Policy link directly below the Hero CTA group was removed; the policy link remains in the page's lower CTA/footer navigation.

## 11. Kids Safe: Parent Control — current website status

- Kids Safe is listed on Home and in the Apps directory.
- There is currently no dedicated Kids Safe detail page at `/apps/kids-safe/`. Do not create one unless requested.
- Google Play URL supplied by the user: `https://play.google.com/store/apps/details?id=org.app.kidsmode` (package `org.app.kidsmode`).
- Privacy Policy pages exist at `/privacy/kids-safe/` (English) and `/privacy/kids-safe/vi/` (Vietnamese).
- The Home card was updated on 18/11/2026 to use the shared `.app-card` visual structure consistent with App Locker, with category text `ANDROID · PARENTAL CONTROLS`, the existing Kids Mode/Allowed apps/Parent PIN tags, a direct Google Play CTA, a Privacy Policy link and an `ANDROID` status label.
- The Apps directory card was aligned with the Home card on 23/11/2026: it now uses the same category, description, tags, Google Play CTA, Privacy Policy link and `ANDROID` status label. It retains the `standalone` modifier for the directory page layout.
- Kids Safe V1 scope and privacy details are recorded in Section 5. Do not overstate remote control or cloud family-management functionality.

## 12. Shared navigation

- The global Privacy navigation points to `/privacy/`.
- The Privacy Directory links each app to its own policy.
- Kids Safe retains English and Vietnamese policy pages; App Locker currently has English only.

## 13. Thông tin liên hệ website

- Brand: Smart Mobile Solution (SMS)
- Support: `help.mobilesolution@gmail.com`
- Website: https://smartmobilesolution.github.io/sms-tools/
- Repository: https://github.com/SmartMobileSolution/sms-tools


## 14. Current verified handoff checkpoint — 18 November 2026

This section is the latest operational snapshot and supersedes earlier notes where details may have become stale.

### Repository and deployment

- Repository: `SmartMobileSolution/sms-tools`.
- Branch: `main`.
- Website source/content baseline: `041a961de459a9656411134bcd18fe6aa7555a14` — `Align Kids Safe home card with App Locker`; GitHub Pages workflow #48 completed with conclusion `success` for this website version: https://github.com/SmartMobileSolution/sms-tools/actions/runs/44338980484.
- Documentation-only handoff update: `b6bf3fbb7e6e203dd041ce0934dc284c936986bc` — `Update website documentation and handoff`. This is the repository HEAD at the time this section was prepared.
- GitHub Pages workflow #49 was triggered by the documentation commit and was still `in_progress` at the last check: https://github.com/SmartMobileSolution/sms-tools/actions/runs/44340526375. It should be checked before claiming the documentation commit's Pages workflow is complete; website source was not changed by that documentation-only commit.
- Live website: https://smartmobilesolution.github.io/sms-tools/.
- Home: https://smartmobilesolution.github.io/sms-tools/.
- Apps directory: https://smartmobilesolution.github.io/sms-tools/apps/.
- App Locker detail: https://smartmobilesolution.github.io/sms-tools/apps/app-locker/.
- App Locker Privacy Policy: https://smartmobilesolution.github.io/sms-tools/privacy/app-locker/.
- Kids Safe Privacy Policy EN: https://smartmobilesolution.github.io/sms-tools/privacy/kids-safe/.
- Kids Safe Privacy Policy VI: https://smartmobilesolution.github.io/sms-tools/privacy/kids-safe/vi/.

### Relevant recent commits

| Commit | Change |
|---|---|
| `f9ec3a8` | Improve App Locker hero icon asset and remove duplicate Hero Privacy link |
| `83d2b93` | Add App Locker screenshot gallery |
| `e0c75ab` | Remove decorative frame around App Locker icon |
| `041a961` | Align Kids Safe Home card with App Locker card and add its Play Store link |

### Owner authorization and boundaries

- The owner explicitly authorized direct work on this repository, including editing and committing/pushing to `main` when a task is assigned.
- Do not merge branches or pull requests.
- Do not modify GitHub Pages configuration, workflows, branch protection, repository settings or other repository configuration unless the owner separately and explicitly authorizes that specific change.
- Always inspect the live HEAD before editing and use a non-forced, expected-head ref update to avoid overwriting concurrent work.

### Next-agent starting checklist

1. Read this handoff and `README.md`.
2. Fetch the current `main` HEAD and inspect the relevant files; the recorded commit is a checkpoint, not a substitute for fresh inspection.
3. Check the current GitHub Pages workflow if a task depends on the public website state.
4. Preserve the existing static HTML/CSS/JS architecture unless a task explicitly calls for a structural change.
5. Do not claim that Kids Safe has a detail page: it currently has Home/App directory cards, Play Store URL and EN/VI Privacy Policy pages only.
6. Do not claim that App Locker has a Vietnamese Privacy Policy: only the English page currently exists.
7. Preserve the supplied PNG screenshot originals; any future WebP conversion should be additive or explicitly approved.


## 15. Current verified source checkpoint — 23 November 2026

- Updated `apps/index.html` so the Kids Safe card matches the Home card's approved content and calls to action.
- The Apps Directory card retains `.app-card standalone`; the `standalone` modifier is a page-layout variant and was intentionally preserved.
- Kids Safe card content is now aligned across Home and Apps Directory:
  - Category: `ANDROID · PARENTAL CONTROLS`.
  - Description: `Help manage which apps children can access when borrowing a parent's Android phone, with allowed-app lists and time-limited Kids Mode sessions.`
  - Tags: `Kids Mode`, `Allowed apps`, `Parent PIN`.
  - Google Play CTA: `https://play.google.com/store/apps/details?id=org.app.kidsmode`.
  - Privacy Policy CTA: `../privacy/kids-safe/` from the Apps Directory.
  - Status: `ANDROID`.
- Source commit: `78449ab9f599ab6d3bdcc21bb56e7666510eb0a5` — `Align Kids Safe card in Apps directory with Home`.
- D-01 — Kids Safe card content alignment: **COMPLETED**. The owner confirmed the live Apps Directory display is correct on 23/11/2026. GitHub Pages workflow #51 for HEAD `57c34da8f59c97ad1057e9254df32a00dc244964` completed successfully: https://github.com/SmartMobileSolution/sms-tools/actions/runs/45190748166.


## 16. Owner decisions and follow-up — 23 November 2026

- D-03 — App Locker Privacy Policy language: **CLOSED / NOT REQUIRED**. The owner confirmed that a Vietnamese version is not needed. Keep the existing English-only policy; do not create a Vietnamese policy page or language switch for App Locker.
- D-04 — App Locker screenshot gallery optimization: **SOURCE MAPPING UPDATED**. Five `.webp` files now exist at `assets/images/app-locker/screenshots/screen-01.webp` through `screen-05.webp`, and `apps/app-locker/index.html` references them. The five files total 576,? bytes (verify from current tree before publishing any exact aggregate).


## 17. Pictarow: Photo to Table — Privacy Policy and Terms of Use

- Owner-provided source content files: `privacy-policy.md` and `terms-of-use.md`.
- Published Privacy Policy: `/privacy/pictarow/` (English), intended as the shared policy for iOS and Android.
- Published Terms of Use: `/terms/pictarow/` (English).
- Both pages use the existing static HTML/CSS/JS site shell and shared stylesheet, with responsive contents navigation and cross-links between the two legal pages.
- Pictarow was added to the Privacy Directory at `/privacy/`; the directory entry links to both legal pages.
- Effective date specified by the owner for both documents: **20 February 2022**.
- Governing law in the Terms of Use: **Vietnam**.
- Subscription wording reflects the owner's commercial decision: free access is ad-supported and may require viewing ads to use features; Premium is a paid monthly or yearly auto-renewing subscription providing unlimited recognition, optional iCloud Sync on iOS and an ad-free experience. **No Premium free trial is offered.**
- Owner-confirmed platform behavior for the shared Privacy Policy:
  - Image/table recognition is performed entirely on-device on both iOS and Android. User photos and table contents are not uploaded to SMS servers or sent to a third-party OCR service.
  - iOS: optional Premium iCloud Sync uses Apple's CloudKit.
  - Android v1: no cloud backup or synchronization is available. Do not state that Android currently uses Google Drive. The owner plans to use Google Drive API for a future Android cloud feature; update the policy when that feature is implemented and ready for release.
  - Both platforms use Firebase Analytics, Firebase Crashlytics, Firebase Remote Config, Google AdMob and Google UMP.
  - iOS subscriptions are handled by Apple App Store / StoreKit; Android subscriptions are handled by Google Play / Google Play Billing.
- The Privacy Policy page was updated to distinguish platform behavior for local data, cloud sync/backup, advertising, purchases, third-party services, retention/deletion and device security. It retains the common policy URL and the owner's effective date.
- Source implementation commits: `4f1e0c5` (original Privacy Policy), `13632cf` (Terms of Use), `a3c23e7` (Privacy Directory), `540aac1` (README), and `e99f86b` (platform-specific Privacy Policy update).
- Legal content is based on owner-confirmed product behavior; publication is not a legal opinion or independent audit of app implementation. Before release, confirm production SDK configuration, data flows, subscription behavior, platform privacy disclosures and app UI match these statements, and consider qualified legal review of the documents.


## 18. Screenshot asset update — 23 November 2026

- Owner committed five App Locker screenshots as WebP under `assets/images/app-locker/screenshots/screen-01.webp` … `screen-05.webp`; the detail page gallery references those WebP paths.
- Owner committed six Kids Safe screenshots as WebP under `assets/images/kids-safe/screenshots/screen-01.webp` … `screen-06.webp`.
- Kids Safe icon remains unchanged at `assets/images/kids-safe-icon.svg`, per owner instruction.
- No Kids Safe detail page has been created yet. These six images are ready for mapping when implementing `/apps/kids-safe/`; do not infer screenshot captions or features solely from filenames. Confirm screenshot contents before writing descriptive alt text/captions.
- Current repository HEAD before this documentation update: `4fa5741708cd30ec6602f30121d10c9459601012` — `Update screenshot for kid-safe`.
