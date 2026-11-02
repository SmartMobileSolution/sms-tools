# TÀI LIỆU BÀN GIAO WEBSITE — SMART MOBILE SOLUTION (SMS)

**Ngày lập:** 02/11/2026  
**Repository:** `SmartMobileSolution/sms-tools`  
**Branch:** `main`  
**Website:** https://smartmobilesolution.github.io/sms-tools/

> Tài liệu này chỉ bàn giao những công việc đã thực hiện trong phạm vi xây dựng và cập nhật website Smart Mobile Solution. Không phải tài liệu bàn giao source code ứng dụng Android Kids Safe.

## 1. Mục tiêu và phạm vi website

Website là trang giới thiệu Smart Mobile Solution (SMS), danh sách ứng dụng, thông tin liên hệ và các trang Privacy Policy tương ứng với từng ứng dụng. Website hiện được tổ chức theo dạng static website với HTML, CSS và JavaScript; không ghi nhận framework frontend hoặc quy trình build riêng trong các file đã xử lý.

## 2. Công việc đã thực hiện

- Xây dựng/chỉnh sửa trang chủ giới thiệu Smart Mobile Solution, thông điệp thương hiệu, khu vực Our Apps và các liên kết điều hướng.
- Xây dựng/chỉnh sửa trang danh sách ứng dụng tại `/apps/`, hiện có thẻ giới thiệu **Kids Safe: Parent Control**.
- Xây dựng/chỉnh sửa trang Contact với email hỗ trợ `help.mobilesolution@gmail.com`.
- Soạn và cập nhật Privacy Policy cho Kids Safe: Parent Control bằng tiếng Anh và tiếng Việt.
- Tinh chỉnh giao diện dùng chung trong stylesheet: màu sắc xanh/teal, typography, card, navigation, trang policy và responsive cho màn hình nhỏ.
- Thay tham chiếu logo công ty từ `company-logo.svg` sang `company-logo.png` trên các trang HTML. Người dùng đã tự commit ảnh PNG gốc và xóa SVG cũ; phần code đã được cập nhật để trỏ đến PNG.
- Thay icon minh họa chữ K trên thẻ ứng dụng bằng ảnh tại `assets/images/kids-safe-icon.svg`.

## 3. Repository và cấu trúc file hiện tại

| Đường dẫn | Vai trò |
|---|---|
| `index.html` | Trang chủ |
| `apps/index.html` | Danh sách ứng dụng |
| `contact/index.html` | Trang liên hệ |
| `privacy/kids-safe/index.html` | Privacy Policy — English |
| `privacy/kids-safe/vi/index.html` | Privacy Policy — Tiếng Việt |
| `assets/css/styles.css` | Stylesheet dùng chung, responsive |
| `assets/js/site.js` | JavaScript dùng chung; hiện được gọi ở cuối các trang để hỗ trợ tiện ích website như năm ở footer |
| `assets/images/company-logo.png` | Logo công ty dạng PNG do người dùng upload/commit; HTML hiện trỏ đến file này |
| `assets/images/kids-safe-icon.svg` | Icon Kids Safe đang được hai trang Home và Apps tham chiếu |

### Các URL hiện có

- Home: https://smartmobilesolution.github.io/sms-tools/
- Apps: https://smartmobilesolution.github.io/sms-tools/apps/
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
> Với mỗi yêu cầu: (1) kiểm tra source và asset liên quan; (2) đề xuất kế hoạch ngắn nếu thay đổi nhiều file; (3) chỉnh sửa tối thiểu; (4) kiểm tra relative links, ảnh, favicon, responsive và các trang ngôn ngữ; (5) kiểm tra diff; (6) commit/push chỉ khi được cấp quyền và người dùng yêu cầu; (7) báo cáo rõ file, URL và các điểm còn chưa xác minh. Không tuyên bố đã kiểm tra live site nếu chưa thực sự kiểm tra.

## 9. Cách bàn giao cho agent mới

1. Tải file DOCX hoặc Markdown này về máy.
2. Mở một cuộc trò chuyện mới với agent muốn bàn giao. Nếu agent làm việc trực tiếp trên GitHub, kết nối/cấp quyền truy cập repository `SmartMobileSolution/sms-tools` trước.
3. Đính kèm file bàn giao vào cuộc trò chuyện mới.
4. Dán prompt ở Mục 8. Nêu thêm yêu cầu cụ thể đầu tiên bạn muốn agent xử lý.
5. Yêu cầu agent xác nhận đã đọc tài liệu, kiểm tra repository/branch hiện tại và tóm tắt trạng thái thật trước khi thực hiện thay đổi.
6. Với agent chạy local, yêu cầu clone repository, checkout `main`, kiểm tra source và commit gần nhất trước khi code. Không gửi token, mật khẩu hoặc thông tin bí mật trong prompt.

## 10. Thông tin liên hệ website

- Brand: Smart Mobile Solution (SMS)
- Support: `help.mobilesolution@gmail.com`
- Website: https://smartmobilesolution.github.io/sms-tools/
- Repository: https://github.com/SmartMobileSolution/sms-tools
