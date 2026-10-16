---
name: "linkedin-event-post"
description: "Draft or revise Nash's LinkedIn posts recapping an event he took part in (conference, talk, workshop, competition), in his voice, English first with a Chinese version."
---

# LinkedIn 活動紀錄貼文（Event recap post）

用於 Nash 想把參加過的活動（研討會、講座、workshop、比賽、參訪、論壇、志工）寫成 LinkedIn 貼文時。範本來自 APMC 2026 橫濱那篇貼文、2026 Innovation Intelligence Hackathon（Upshift 得獎）那篇貼文的修改過程，以及 TECO SF 國慶酒會志工、SEMICON West Taiwan Supply Chain Forum 兩篇。

## 1. 先蒐集素材，再動筆

依序查找，找到的事實才可以寫進貼文：

1. 記憶檔：profile、相關 /areas/ 與 /people/ 檔案，以及專案裡的紀錄文件
2. 過去對話（conversation_search）：活動準備、簡報、信件、IG 文案，以及同一位同行者在過去貼文中的 tag 寫法
3. 他電腦上存放活動資料的資料夾：議程、接受信、證書、content brief
4. 他貼上的照片：證書、頒獎投影片、桌牌、海報、議程看板、背板。從照片確認獎項名稱、track、隊名寫法、主辦／協辦／贊助單位 logo、講者姓名與職稱
   - 照片若是 .HEIC，先 `pip install --break-system-packages pillow-heif`，用 PIL + ImageOps.exif_transpose 轉成 jpg 再讀
5. 活動官網：主辦單位、track 名稱、獎項名稱
6. 日記或個人筆記：讀不到時，請 Nash 貼上那幾天的整理（日期、時間點、遇到的人、他自己寫下的原句），不要用猜的

他貼的活動筆記常是自動逐字稿或 AI 摘要，人名、職稱、專有名詞常被聽錯（例如名字被聽成發音相近的另一個名字，或把 "AI" 聽成別的縮寫）。人名與職稱一律以議程照片、桌牌、官網為準；筆記和照片對不上的地方，在全文後列出請他確認，無法確認的內容就不寫進貼文。

素材不足時，先寫草稿並用 [ ] 標出要他補的地方（例如贊助商、評審名單），不要編造現場細節、情緒或觀眾反應。

## 2. 事實與署名規則

- 共同作者論文：寫 "With A and Prof. B, I presented..."，不要寫成他一個人的研究。提醒他 tag 共同作者
- 指導教授的英文名以其官方寫法為準，不要自己用拼音推
- 無法確認時，不寫「第一次」、人數、觀眾反應
- 數字以他確認的說法為準。他的數字和紀錄不同時（例如紀錄是 7 次訪談，他寫 nearly 10），提醒一次，之後照他的版本
- 他用的專有名詞照原樣保留（例如 "IIH Stack" 是活動的組隊平台），看起來像錯字時先問，不要自己改成別的字
- 隊名、產品名照團隊自己的品牌寫法（例如 "upshift." 小寫加句點）
- 人名用對方 LinkedIn 上的顯示名稱，方便 tag（例如寫 Jane Doe，不寫成 Jane (JD) Doe）
- 同行者（一起參加的朋友、隊友）若他只給暱稱，動筆前或在全文後問他對方的 LinkedIn 顯示名稱。全文同一個人只用一種稱呼：tag 用顯示名稱，後文提到也用同一個名字，不要開頭 tag 全名、結尾又寫暱稱
- 組織用 LinkedIn 粉專的完整名稱（例如 UC Berkeley Sutardja Center for Entrepreneurship and Technology (SCET)）。同名組織有多個分處時（例如 TECO 各地辦事處），提醒他確認 tag 的是正確那一個粉專
- 從英文名推出來的中文姓名、公司中文名，請他發文前確認
- NVIDIA 研究的描述：用「平台業者進入互補財市場（platform owner entry, POE）」，英文寫 "how a platform owner signals trustworthiness to its complementors when it enters their market"。不要寫成「跟合作夥伴競爭」
- STM Service 的由來（他確認過的說法）：每個人在 R 裡跑 STM 的參數設定都不同，第一次接觸的人不好上手，所以做給研究室用

## 3. 結構

先判斷他在活動中的角色，再選結構。

### 3a. 研討會、講座、參訪，他有發表或被邀請（APMC 版本）

1. 第一句：如果是事後補寫，用一句帶過時間差，例如 "Almost five months late, but I still wanted to write this down."（中文：「晚了快五個月，但還是想把這段經驗記錄下來。」）。不要用 "deal with my LinkedIn!" 這類把主角變成 LinkedIn 的說法
2. 第二段：交代最重要的那件事，誰邀請、什麼活動、在哪裡、用什麼語言、對象是誰。要放在前兩三行，因為 LinkedIn 只顯示這麼多就折疊成「…see more」
3. 一句活動背景（主辦單位），接著寫他做了哪些事
4. 他的任務用段落文字寫在文章裡，不要用編號或列點。每件事寫做了什麼，最多留一個具體細節（例如會後誰帶他逛校園、送了什麼）
5. 一句感謝（邀請人、主辦方）
6. hashtag

### 3b. 比賽得獎（Hackathon 版本）

1. 第一句：隊名、獎項全名（含 track）、名次、活動名稱、學校。可以用一個驚嘆號結尾
2. 怎麼加入團隊：在哪裡找隊伍、誰邀請，順帶感謝並 tag 每位隊友
3. 活動背景（主辦單位、活動性質）＋用兩三句短句說明做了什麼產品
4. 他的角色寫成一段文字：負責什麼、做了什麼（含數字）、和隊友一起調整了什麼、評審給了什麼方向
5. 一句得獎感受（例如 "We are really honored to win."）＋賽後做了什麼，接著同一段感謝：主辦單位、贊助商、評審、主持人，全部 tag
6. 單獨一句收尾（例如 "It was a wonderful day."）
7. hashtag：活動 hashtag（如 #SFTechWeek）、活動名、學校、隊名，約 3 到 4 個

### 3c. 純參加者或志工（SEMICON West 論壇、TECO 國慶酒會版本）

他沒有上台、只是出席或幫忙時，用這個短版本。即使他貼了很長的逐講者筆記，第一版也不要把每位講者寫進去。

1. 第一句：和誰、參加了什麼活動、在哪裡、什麼時候（例如 "I joined the Taiwan Supply Chain Forum at SEMICON West in San Francisco today with [friend's name]."）
2. 一段活動背景：主辦、協辦、贊助單位，以及活動主軸（一兩句）
3. 一句帶過議程內容（例如 "The forum included remarks from government representatives, keynotes from Intel and Micron, and talks from four Taiwanese suppliers..."）。志工則寫他負責什麼（例如 guest check-in, guiding guests）
4. 緊接一句簡短收穫（見第 4 節）
5. 一句感謝：主辦單位＋同行者
6. hashtag 約 3 到 4 個

全文後可以問他要不要挑一兩個具體細節（一句引言、一個數字）加回去，但不要預設加入。

## 4. 語氣（他的口吻）

- 以紀錄過程為主。不寫長篇心得：心情描寫、「像出差」、壓力、不緊張、「用兩個字總結」、lessons learned 清單
- 可以保留一句簡短、平實的收穫，放在內容段落結尾（他在 TECO、SEMICON 兩篇都主動要求保留）。例如 "I met people from many different backgrounds, and talking with them broadened my perspective." 或 "I was glad to see so many examples of Taiwan-US supply chain collaboration in one afternoon, and I will keep learning more about this industry." 得獎貼文則是一句 honored 加一句收尾
- 不要讓人覺得在炫耀。不把「大學生」和「自己做的工具」並排強調，改成說明為什麼做這個工具，讓它讀起來像順手解決問題
- 英文用短句、常用字，像台灣大學生自然寫的英文，不追求華麗修辭
- 同一個開頭詞或情緒詞全文只用一次（例如 "I was glad" 不要同時出現在第一句和收穫句）
- 拿掉 AI 痕跡：粗體小標、整齊的三點結論、金句（「這句話教我的比任何投影片都多」）、過度對稱的收尾
- 內文不用編號或列點，寫成段落
- 不用破折號（—）、emoji、Unicode 粗體字（𝗹𝗶𝗸𝗲 𝘁𝗵𝗶𝘀）
- 中文避免「不只是／不再只是…而是…」「不僅…更…」，也避免 AI 式開場
- LinkedIn 不支援 Markdown，貼文本體裡不要出現 ** 或 #標題（hashtag 除外，內文中也可以直接放活動 hashtag，例如 "an official #SFTechWeek event"）

## 5. 輸出方式

- 先給英文版（主要），再給中文版
- 直接在對話裡輸出文字，不建立檔案，也不要用 message_compose（中文會出現錯字）
- 每次修改，不論改多少，都回傳完整的全文（英文版和中文版都給），不要只給替換段落
- 他說「刪除」就完整刪除，不改寫成較短的版本保留；刪除後若留下太短的孤句，提醒他可以併段或拿掉
- 他說「縮短」某幾段時，把那幾段合併成一段概述，保留他指定要強調的意思
- 他問英文用詞（例如 "kept breaking" 是什麼意思）時，拆解片語說明，並確認這個說法是否符合他的實際情況，再提供替代說法
- 全文之後，用簡短清單列出還沒補的 [ ]、筆記與照片對不上的人名、要 tag 的對象

## 6. 他貼回最終版時

他常會把自己在 LinkedIn 編輯器裡改好的最終版（含 tag 連結）貼回來。這時只做校對，不重寫全文，列出問題即可；他要求修正時再給完整全文：

- 同一個人前後稱呼是否一致（tag 名稱 vs 後文暱稱）
- 重複的開頭詞或用字
- 句子中間被斷行（從編輯器複製常出現），以及段落之間是否缺空行
- tag 的粉專是否正確（同名組織、不同分處）
- 該 tag 而沒 tag 的組織或人

## 7. 發文前檢查清單

- 每個事實都能對應到素材來源；人名、職稱以照片或官網為準，不以逐字稿為準
- 共同作者與署名順序正確，tag 對象列好（隊友、同行者、主辦單位、贊助商、評審、主持人）
- 人名與組織名稱和 LinkedIn 顯示名稱一致，同一人全文只有一種稱呼
- 前兩三行已經講到最重要的事
- 沒有長篇心得、沒有破折號、沒有 Markdown 符號、沒有列點
- 沒有重複的開頭詞（例如兩個 "I was glad"）
- 文法小地方："thanks to"（不是 "thanks for" + 人）、名單結尾不要多一個句點、最後一個 hashtag 後面不加句點
- 中英文版本內容一致