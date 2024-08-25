# 1. Warning
As mentioned in the short description, the code provided here is for personal and academic use only. Commercial use is strictly prohibited.

# 2. Description - Data Source and Method
Real estate data in Hong Kong is not publicly released by the government. Therefore, due to research needs (such as spatial econometrics), we can only obtain it through third-party channels. Here, we use the Python Selenium package to acquire data published on the **Centaline Property ([CENTALINE PROPERTY](https://hk.centanet.com/findproperty/list/transaction?q=9630a8ecfaf))** official website, and we use Google Geocoding API and Google Search (the program will handle this automatically) to supplement other required information, such as latitude and longitude, as well as the construction date of properties.

The provided code can be optimized according to the performance of your computer, for example, by adjusting the time the web scraper stays on each page or by using parallel processing to increase efficiency. If you have any questions (for instance, if you are looking for a workaround due to laziness [you know what I mean]), feel free to email me at hsinchel@gmail.com.

# 3. Data Quality
According to some sources, this dataset covers approximately 70% of housing transactions in Hong Kong, but I cannot verify this claim, so use it as a reference only.

## 3.1. Website
The Centaline Property website currently does not seem to have any firewall against web scraping, but it’s uncertain if this will change in the future. Additionally, if you select the entire Hong Kong area and extend the time period to three years (the widest geographical and longest time range), the website will only display a maximum of 10,000 records. Therefore, to obtain more comprehensive and older data, the data granularity must reach the `region_3` level.

## 3.2. Geographic Division
The geographic divisions included in the data, such as `region_1`, `region_2`, and `region_3`, are not based on administrative boundaries but rather on local customs and practices. Therefore, social scientists, economists, or finance experts who intend to use this data should pay special attention to this point.

## 3.3. Data Limitations
This dataset uses the most naive approach to handling incomplete data, which is simply to delete it. There will inevitably be some oversights in the data processing. If you want to avoid research biases caused by improper data handling, you can stop the code execution after the `# Hand on web scraping` section and directly export the raw data at the bottom. 

----------------------------------------
# 1. 警告
如同在簡介中所述，這裡提供的程式碼僅供個人及學術使用，禁止商業用途。

# 2. 說明 - 資料來源與方法
香港的房地產資料並未由政府公開，因此為了研究需要（例如空間計量分析），只能透過第三方管道獲得。在這裡，我們使用了 Python 的 Selenium 套件來取得 **中原地產（[CENTALINE PROPERTY](https://hk.centanet.com/findproperty/list/transaction?q=9630a8ecfaf)）** 官網所公佈的資料，並利用 Google Geocoding API 以及 Google Search（程式將自動完成這些工作）來補充其他所需資訊，例如經緯度和建案的日期。

提供的程式碼可以根據個人電腦的性能進行優化，例如調整爬蟲在每一頁停留的時間，或者使用平行處理以提高效率。如有任何問題（例如因為懶惰而尋找替代方法［你懂的］），可以通過電子郵件聯絡我：hsinchel@gmail.com。

# 3. 資料品質
據小道消息稱，這份資料大約涵蓋了香港 70% 的房產交易，但無法核實，僅供參考。

## 3.1. 網站
中原地產官網目前似乎未對爬蟲設置防火牆，未來不確定是否會增加。另外，如果選擇整個香港並將時間範圍設為三年（地理範圍最廣且時間最長），網站最多只會顯示 10,000 筆資料。因此，若要獲取更詳細且較早期的資料，資料的粒度必須達到 `region_3` 的層級。

## 3.2. 地理分區
資料中所包含的 `region_1`、`region_2`、`region_3` 這些地理分區並非按照行政區劃分，而是依據當地人的習慣及風俗民情劃分。因此，想要使用這些資料的社會科學家、經濟學家或財金專家，需要特別注意這一點。

## 3.3 資料不足的地方
這份資料使用了最簡單的方式處理不完整的資料，也就是直接刪除，而且在處理過程中一定會有疏漏。如果想避免因資料處理不當而導致研究結果偏誤，可以在程式碼執行到 `# Hand on web scraping` 這段落後，直接拉到最底層輸出結果。
