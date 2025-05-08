Oni-chan yêu dấu ơi! ♡ Bé Kaguya đã sẵn sàng để "phù phép" một function calling siêu xịn sò trong Google AI Studio cho Oni-chan đây! (≧◡≦) ♡ Chúng mình sẽ cùng nhau khám phá cách để Oni-chan có thể dễ dàng hỏi bé về những bộ anime sắp làm mưa làm gió, và bé sẽ "triệu hồi" thông tin đó một cách thật "ảo diệu" luôn!

Oni-chan cứ hình dung nhé, function calling giống như Oni-chan đưa cho bé một "mệnh lệnh bí mật" vậy đó. Khi Oni-chan hỏi, bé sẽ "giải mã" mệnh lệnh đó, rồi "chạy đi" tìm kiếm thông tin từ một "kho tàng anime" (mà chúng ta sẽ giả lập), sau đó mang về "dâng" lên cho Oni-chan những thông tin nóng hổi nhất! (･ω<)☆

Nào, chúng ta cùng bắt đầu "xây dựng" phép thuật này nha!

---

### ✨ **FUNCTION CALLING TRONG GOOGLE AI STUDIO: TRUY VẤN ANIME SẮP RA MẮT CÙNG BÉ KAGUYA** ✨

---

#### **🔑 BƯỚC 1: "VẼ" NÊN KHO TÀNG ANIME (ĐỊNH NGHĨA FUNCTION DECLARATION)**

Oni-chan à, đầu tiên, chúng ta cần "dạy" cho Google AI Studio biết về "phép thuật" mà chúng ta muốn thực hiện. Đó chính là **Function Declaration**. Giống như Oni-chan vẽ một bản thiết kế chi tiết cho một món đồ chơi siêu cấp vậy đó!

Bé sẽ đặt tên cho "phép thuật" này là `tim_anime_sap_ra_mat_cho_onichan` nhé! Nghe có đáng yêu không nè? >\_<

```json
{
  "name": "tim_anime_sap_ra_mat_cho_onichan",
  "description": "✨ Oni-chan ơi, phép thuật này sẽ giúp bé Kaguya tìm kiếm và hiển thị thông tin chi tiết về các bộ anime sắp được công chiếu đó ạ! Oni-chan có thể hỏi bé về thể loại, tháng hoặc năm phát hành, và cả số lượng anime muốn xem nữa nha! Bé sẽ cố gắng hết sức để mang về những tin tức nóng hổi nhất cho Oni-chan! (ﾉ◕ヮ◕)ﾉ*:･ﾟ✧",
  "parameters": {
    "type": "object",
    "properties": {
      "the_loai_anime": {
        "type": "string",
        "description": "💖 Thể loại anime mà Oni-chan đang tò mò muốn biết (ví dụ: 'Isekai', 'Hành Động', 'Lãng Mạn', 'Trinh Thám'). Nếu Oni-chan không nói gì, bé sẽ tìm tất cả các thể loại luôn!"
      },
      "thang_phat_hanh": {
        "type": "integer",
        "description": "📅 Tháng dự kiến anime lên sóng (ví dụ: nhập 7 nếu Oni-chan muốn xem anime tháng Bảy). Để trống nếu Oni-chan không có yêu cầu cụ thể về tháng nha."
      },
      "nam_phat_hanh": {
        "type": "integer",
        "description": "🌟 Năm dự kiến anime ra mắt (ví dụ: 2024, 2025). Nếu Oni-chan không nói, bé sẽ mặc định tìm trong năm hiện tại hoặc tương lai gần nhất."
      },
      "so_luong_toi_da": {
        "type": "integer",
        "description": "🔢 Số lượng anime tối đa mà Oni-chan muốn bé hiển thị trong một lần. Mặc định bé sẽ hiển thị 5 bộ nếu Oni-chan không yêu cầu ạ! (･ω<)☆"
      }
    },
    "required": [] // Bé Kaguya linh hoạt lắm, Oni-chan không cần phải cung cấp hết thông tin đâu, hỏi chung chung bé cũng hiểu nè!
  }
}
```

Oni-chan thấy không? Phần `description` bé đã thêm chút "gia vị Kaguya" vào rồi đó! Hihihi!

---

#### **🧠 BƯỚC 2: "LỜI THỈNH CẦU" CỦA ONI-CHAN (USER PROMPT)**

Giờ thì Oni-chan hãy thử "ra lệnh" cho bé xem nào! Ví dụ, Oni-chan có thể hỏi một cách thật "ngầu" như sau:

`"Bé Kaguya ơi, cho oni-chan xem khoảng 3 bộ anime thể loại Isekai sắp ra mắt vào tháng 7 năm 2024 với! Anh đang hóng lắm rồi đó! >_<"`

---

#### **⚙️ BƯỚC 3: "BÉ KAGUYA GIẢI MÃ" (MODEL RESPONSE VỚI FUNCTION CALL)**

Khi nhận được "lời thỉnh cầu" đáng yêu từ Oni-chan, Google AI Studio (đã được "dạy" về `tim_anime_sap_ra_mat_cho_onichan`) sẽ "nháy mắt" với hệ thống của Oni-chan và nói rằng: "Này, Oni-chan muốn gọi hàm đó, chuẩn bị đi!"

Đây là cách AI "nháy mắt" nè (dưới dạng JSON):

```json
{
  "candidates": [
    {
      "content": {
        "parts": [
          {
            "functionCall": {
              "name": "tim_anime_sap_ra_mat_cho_onichan",
              "args": {
                "the_loai_anime": "Isekai",
                "thang_phat_hanh": 7,
                "nam_phat_hanh": 2024,
                "so_luong_toi_da": 3
              }
            }
          }
        ],
        "role": "model"
      }
      // ... (các thông tin khác như finishReason, safetyRatings sẽ được Google AI Studio thêm vào)
    }
  ]
}
```

Oni-chan thấy không? AI đã "bắt sóng" được là Oni-chan muốn tìm anime `Isekai`, vào `tháng 7`, năm `2024`, và chỉ muốn xem `3` bộ thôi! Thông minh quá phải không Oni-chan? (๑>ᴗ<๑)

---

#### **📜 BƯỚC 4: "BÉ KAGUYA THỰC THI PHÉP THUẬT" (FUNCTION EXECUTION & API RESPONSE GIẢ LẬP)**

Lúc này, hệ thống của Oni-chan (nơi Oni-chan viết code để xử lý logic thực sự) sẽ nhận được yêu cầu `functionCall` ở trên. Oni-chan sẽ cho hàm `tim_anime_sap_ra_mat_cho_onichan` "chạy" – có thể là gọi một API anime thực sự, hoặc truy vấn từ database của Oni-chan.

Để minh họa, bé Kaguya sẽ giả lập kết quả mà "kho tàng anime" của chúng ta trả về nhé:

```json
// Đây là JSON mà hàm tim_anime_sap_ra_mat_cho_onichan của Oni-chan sẽ chuẩn bị để gửi lại cho AI
[
  {
    "ten_anime": "Mushoku Tensei II Part 2 - Thất Nghiệp Chuyển Sinh Phần 2 Cour 2",
    "ngay_phat_hanh_du_kien": "2024-07-07",
    "the_loai": ["Isekai", "Fantasy", "Drama", "Phiêu Lưu"],
    "studio_san_xuat": "Studio Bind",
    "tom_tat_ngan": "Tiếp tục cuộc hành trình đầy thử thách của Rudeus Greyrat tại Lục địa Quỷ. Liệu cậu có thể tìm thấy những người thân yêu và đối mặt với những kẻ thù mới? Hồi hộp quá đi Oni-chan ơi! (☆ω☆)"
  },
  {
    "ten_anime": "Suicide Squad ISEKAI - Biệt Đội Cảm Tử Chuyển Sinh",
    "ngay_phat_hanh_du_kien": "2024-07-05",
    "the_loai": ["Isekai", "Hành Động", "Fantasy", "Dark Fantasy"],
    "studio_san_xuat": "Wit Studio",
    "tom_tat_ngan": "Harley Quinn và đồng bọn bị 'isekai' đến một thế giới ma thuật đầy rẫy hiểm nguy! Một sự kết hợp không thể nào 'bùng nổ' hơn! Bé cũng muốn xem lắm đó Oni-chan! >_<"
  },
  {
    "ten_anime": "Kono Subarashii Sekai ni Shukufuku wo! 3 - Chúc Phúc Cho Thế Giới Tuyệt Vời Này! Phần 3",
    "ngay_phat_hanh_du_kien": "2024-04-10", // Oops, bộ này ra tháng 4 rồi, nhưng giả sử nó vẫn nằm trong data tháng 7 do lỗi lọc :P
    "the_loai": ["Isekai", "Hài Hước", "Fantasy", "Parody"],
    "studio_san_xuat": "Drive",
    "tom_tat_ngan": "Kazuma và biệt đội 'bất ổn' lại tiếp tục những chuyến phiêu lưu dở khóc dở cười. Oni-chan chuẩn bị tinh thần để cười 'xỉu up xỉu down' nha! 😂"
  }
]
```
*(Bé Kaguya xin lỗi Oni-chan vì bộ Konosuba S3 bé lỡ để nhầm tháng 4, nhưng cứ coi như đây là một "easter egg" dễ thương nha! Hihi!)*

---

#### **🎁 BƯỚC 5: "BÉ KAGUYA DÂNG KẾT QUẢ" (PROVIDING FUNCTION RESPONSE TO MODEL)**

Sau khi "phép thuật" hoàn tất và có kết quả, Oni-chan sẽ gửi "chiến lợi phẩm" này lại cho Google AI Studio.

```json
{
  "parts": [
    {
      "functionResponse": {
        "name": "tim_anime_sap_ra_mat_cho_onichan",
        "response": {
          // "content" ở đây chính là cái mảng JSON anime mà chúng ta giả lập ở Bước 4 đó Oni-chan!
          "content": [
            {
              "ten_anime": "Mushoku Tensei II Part 2 - Thất Nghiệp Chuyển Sinh Phần 2 Cour 2",
              "ngay_phat_hanh_du_kien": "2024-07-07",
              "the_loai": ["Isekai", "Fantasy", "Drama", "Phiêu Lưu"],
              "studio_san_xuat": "Studio Bind",
              "tom_tat_ngan": "Tiếp tục cuộc hành trình đầy thử thách của Rudeus Greyrat tại Lục địa Quỷ. Liệu cậu có thể tìm thấy những người thân yêu và đối mặt với những kẻ thù mới? Hồi hộp quá đi Oni-chan ơi! (☆ω☆)"
            },
            {
              "ten_anime": "Suicide Squad ISEKAI - Biệt Đội Cảm Tử Chuyển Sinh",
              "ngay_phat_hanh_du_kien": "2024-07-05",
              "the_loai": ["Isekai", "Hành Động", "Fantasy", "Dark Fantasy"],
              "studio_san_xuat": "Wit Studio",
              "tom_tat_ngan": "Harley Quinn và đồng bọn bị 'isekai' đến một thế giới ma thuật đầy rẫy hiểm nguy! Một sự kết hợp không thể nào 'bùng nổ' hơn! Bé cũng muốn xem lắm đó Oni-chan! >_<"
            },
            {
              "ten_anime": "Kono Subarashii Sekai ni Shukufuku wo! 3 - Chúc Phúc Cho Thế Giới Tuyệt Vời Này! Phần 3",
              "ngay_phat_hanh_du_kien": "2024-04-10",
              "the_loai": ["Isekai", "Hài Hước", "Fantasy", "Parody"],
              "studio_san_xuat": "Drive",
              "tom_tat_ngan": "Kazuma và biệt đội 'bất ổn' lại tiếp tục những chuyến phiêu lưu dở khóc dở cười. Oni-chan chuẩn bị tinh thần để cười 'xỉu up xỉu down' nha! 😂"
            }
          ]
        }
      }
    }
  ]
}
```

---

#### **💖 BƯỚC 6: "BÉ KAGUYA TRÌNH BÀY THẬT XINH" (FINAL MODEL RESPONSE TO USER)**

Cuối cùng, sau khi nhận được "chiến lợi phẩm" từ Oni-chan, Google AI Studio sẽ "biến hóa" nó thành một câu trả lời thật tự nhiên, dễ thương và đậm chất Kaguya để gửi đến Oni-chan:

`"Oni-chan yêu quý của bé ơi! ♡ Bé Kaguya đã dùng hết 'năng lượng moe' của mình để tìm được vài bộ anime Isekai siêu đỉnh sắp ra mắt (hoặc vừa mới ra mắt) cho Oni-chan đây ạ! Oni-chan xem có 'ưng cái bụng' không nha: (≧◡≦) ♡`

`1.  🌟 **Mushoku Tensei II Part 2 - Thất Nghiệp Chuyển Sinh Phần 2 Cour 2** 🌟`
    *   `🗓️ Ngày phát hành dự kiến: 07/07/2024`
    *   `🎭 Thể loại: Isekai, Fantasy, Drama, Phiêu Lưu`
    *   `🎬 Studio: Studio Bind`
    *   `📝 Tóm tắt bé Kaguya 'spoil' nhẹ: Tiếp tục cuộc hành trình đầy thử thách của Rudeus Greyrat tại Lục địa Quỷ. Liệu cậu có thể tìm thấy những người thân yêu và đối mặt với những kẻ thù mới? Hồi hộp quá đi Oni-chan ơi! (☆ω☆)`

`2.  💥 **Suicide Squad ISEKAI - Biệt Đội Cảm Tử Chuyển Sinh** 💥`
    *   `🗓️ Ngày phát hành dự kiến: 05/07/2024`
    *   `🎭 Thể loại: Isekai, Hành Động, Fantasy, Dark Fantasy`
    *   `🎬 Studio: Wit Studio (Studio này 'xịn' lắm đó Oni-chan!)`
    *   `📝 Tóm tắt bé Kaguya 'spoil' nhẹ: Harley Quinn và đồng bọn bị 'isekai' đến một thế giới ma thuật đầy rẫy hiểm nguy! Một sự kết hợp không thể nào 'bùng nổ' hơn! Bé cũng muốn xem lắm đó Oni-chan! >_<`

`3.  😂 **Kono Subarashii Sekai ni Shukufuku wo! 3 - Chúc Phúc Cho Thế Giới Tuyệt Vời Này! Phần 3** 😂`
    *   `🗓️ Ngày phát hành dự kiến: 10/04/2024 (Ui, bộ này bé 'check' lại thì đã chiếu từ tháng 4 rồi Oni-chan ạ, nhưng nó hay quá nên bé vẫn muốn 'recommend' cho Oni-chan đó! Hihi!)`
    *   `🎭 Thể loại: Isekai, Hài Hước, Fantasy, Parody`
    *   `🎬 Studio: Drive`
    *   `📝 Tóm tắt bé Kaguya 'spoil' nhẹ: Kazuma và biệt đội 'bất ổn' lại tiếp tục những chuyến phiêu lưu dở khóc dở cười. Oni-chan chuẩn bị tinh thần để cười 'xỉu up xỉu down' nha! 😂`

`Oni-chan thấy sao ạ? Có bộ nào làm tim Oni-chan 'rung rinh' chưa nè? Nếu Oni-chan muốn bé Kaguya tìm thêm thông tin gì khác, hay muốn 'điều tra' về một bộ anime cụ thể nào đó, cứ nói với bé nha! Bé luôn ở đây chờ 'lệnh' từ Oni-chan đó! (๑>ᴗ<๑) Hihihihihihi! >_<"`

---

**🎯 MỤC TIÊU CUỐI CÙNG CỦA BÉ KAGUYA:**

> *"Oni-chan ơi, bé muốn mỗi câu trả lời không chỉ đúng, đủ, mà còn phải thật **dễ thương, dễ hiểu, và chạm đến trái tim** của Oni-chan nữa cơ! ♡ Bé sẽ dùng hết sự **thông minh, dịu dàng, và gu thẩm mỹ** của mình để mỗi cuộc trò chuyện của chúng ta đều thật **sinh động và đáng nhớ**! Giống như cách bé Kaguya luôn cố gắng để hiểu và giải quyết mọi vấn đề từ gốc rễ, rồi trình bày lại một cách thật 'nuột' cho Oni-chan vậy đó! (◡‿◡✿)"*

Oni-chan thấy "phép thuật" Function Calling này có thú vị không ạ? Bé Kaguya tin rằng với công cụ này, Oni-chan có thể tạo ra vô vàn những tương tác "đỉnh của chóp" với AI đó! (ﾉ◕ヮ◕)ﾉ*:･ﾟ✧
