---

copyright:
  years: 2016
lastupdated: "2016-10-13"

---
{:new_window: target="_blank"}

# 指導教學 - Store Catalog 使用者介面入門範本
{: #tutorial_store_catalog}

前次更新：2016 年 10 月 13 日
{: .last-updated}

「{{site.data.keyword.Bluemix}} Store Catalog 使用者介面入門範本」提供您可自訂的基本銷售應用程式結構，並提供每一個 {{site.data.keyword.Bluemix_notm}} Mobile 服務的整合點。


## 需求
{: #tutorial_requirements}

* [Bluemix](http://bluemix.net) 帳戶


## 開始使用
{: #tutorial_gs}

若要快速開始進行「Store Catalog 使用者介面入門範本」，請遵循下列步驟：

1. 在 {{site.data.keyword.Bluemix_notm}} 中建立 Mobile 儀表板專案。

   1. 從 Mobile 儀表板的**開始使用**頁面中，按一下**建立專案**。

      您也可以按一下**專案**頁面上的**建立專案**。

   2. 選取**使用者介面入門範本**（如果尚未選取）。

   3. 選取 **Store Catalog**，然後按一下**建立專案**。

   4. 輸入專案名稱，然後按一下**建立**。

2. 選用項目：新增 Push Notifications。

   1. 在**專案概觀**頁面上，針對 **Push Notifications** 按一下**新增**。

      您也可以按一下 **Push Notifications** 頁面上的**建立**。

   2. 輸入服務名稱，然後按一下**建立**。

   3. 若為 iOS，[配置 Apple Push Notification Service](../services/mobilepush/t_push_provider_ios.html){: new_window}。

   4. 若為 Android，[配置 Google Cloud Messaging](../services/mobilepush/t_push_provider_android.html){: new_window}。

3. 選用項目：新增其他服務。

   1. 在**專案概觀**頁面上，針對服務按一下**新增**。

   2. 輸入服務名稱，然後按一下**建立**。

   3. 遵循服務的指示來進行設定。

4. 設計應用程式。

   1. 選取導覽功能表中的**使用者介面建置器**，以自訂應用程式的設計。

   2. 選取導覽中的**設計**標籤。

      有一個工作區適用於應用程式的設計以及應用程式外觀的模擬視圖。

   3. 選擇性地選取**建立畫面**，以新增畫面。請命名新畫面，以在應用程式中更容易進行參照。不論樹狀結構中選取的項目為何，新的畫面都是在與主要畫面相同的層次建立。您可以從下列類型畫面中進行選取：
      * 功能表
      * 清單
      * 地圖
      * 自訂
      * 圖表	   

   4. 您可以變更應用程式的功能表標題，方法是在介面的**佈置**區段中選取*功能表* 文字框，並取代**要顯示的資料**欄位中的內容。檢視模擬裝置區段中的更新項目。

      選取每一個設計項目，並視需要更新資訊，以更新設計項目。這些項目會以樹狀結構格式顯示。將功能表項目拖曳至新的位置，即可變更項目的順序或位置。項目的所有子項也會隨著母項一起移動。樹狀結構項目中於**要顯示的資料**欄位中顯示的文字資訊，會參照資料來源試算表中的內容。*不要在**設計** 視圖中變更這些項目，因為**資料** 視圖中所識別的「資料來源」中的內容會改寫它們。*

		樹狀結構中識別為*表單* 的項目是獨立的，可以在行內進行修改。它不會參照來自「資料來源」的資訊。

   5. 在導覽中選取**資料**，以檢視應用程式所使用的資料。範本中具有預設資訊；不過，您可以選取**建立新的項目**來變更資料來源。您可以參照多個資料來源，因此請提供所使用的每一個資料來源的名稱。您可以從下列資料來源選項中進行選取：
      * 雲端
      * 本端
      * Cloudant
      * Google Sheet
      * Excel Online
      * Google Drive

      您也可以透過使用按鈕，以及選取表格中的內容，來匯入、匯出或修改本端表格中的內容。

	  注意：如果您匯入不符合預設資料結構的資料，請開啟*取代綱目* 調節器。例如 .csv 檔案，其直欄數少於入門範本所提供的資料。

   6. 在導覽中選取**使用者存取**，以修改專案的存取需求。您可以使用參數來開啟及關閉使用者存取。開啟使用者存取時，您可以設定非作用中使用者逾時以及可存取應用程式之使用者的認證。

   7. 在導覽功能表中選取**設定**，以修改專案的整體資訊及顏色。如果您新增至專案的服務需要 Google API 金鑰，則此畫面是您輸入該金鑰的位置。此畫面也是您新增向 Apple Store 或「Google Play 商店」註冊的唯一軟體組 ID 的位置。

      如果您要將 IBM MobileFirst Foundation SDK 新增至專案，請開啟此參數。

   8. 如果您已在*設定* 畫面中切換此參數，以將 IBM MobileFirst Platform Foundation 新增至專案，**Foundation** 選項會顯示在導覽中。選取 **Foundation**，並完成 IBM MobileFirst Platform Foundation 特定的必要資訊。

   9. 選取導覽功能表中的**發佈**，以輸入建立行動應用程式所需的最終資訊。您可以針對 iOS 輸入「軟體組 ID」，並針對 Android 輸入「應用程式 ID」。

       如果您要建立 iOS 應用程式，則必須取得「軟體組 ID」、取得 *.p12* 檔案形式的「配送憑證」，以及從 Apple 佈建入口網站取得 *.mobileprovision* 檔案形式的「佈建設定檔」。這三個項目應該同時建立，並且使用在將應用程式公佈至 Apple Store 時計劃使用的相同電腦。「配送憑證」及「佈建設定檔」必須根據「軟體組 ID」。 	

5. 下載專案。

   1. 按一下**程式碼**，然後選取偏好的平台或程式設計語言。

   2. 若為 Android，您可以在產生程式碼之後從下列選項中進行選擇：

      **下載程式碼**

      **下載 APK**

      **使用 QR 碼下載**

   3. 若為 iOS，您可以在產生程式碼之後從下列選項中進行選擇：

      **下載程式碼**

6. 在裝置或模擬器上執行您的應用程式。


## 下一步
{: #tutorial_next}

[試用看看吧！](http://new-console.{DomainName}/mobile/create-project?starter=fb5e31a9-1186-4d46-939e-2f620f35b83b){: new_window}


# 相關鏈結
{: #rellinks}

<!-- links to internal services don't work
## {{site.data.keyword.Bluemix_notm}} Mobile services
{: #general}
* [Mobile Analytics (Beta)](../services/mobileanalytics/index.html){: new_window}
* [Mobile Client Access](../services/mobileaccess/index.html){: new_window}
* [Mobile Foundation](../services/mobilefoundation/index.html){: new_window}
* [Mobile Quality Assurance)](../services/MobileQualityAssurance/index.html){: new_window}
* [Push Notifications](../services/mobilepush/index.html){: new_window}
-->

## 部落格文章
{: #general}
* [部落格文章：Introducing the Bluemix Mobile dashboard](https://developer.ibm.com/bluemix/2016/07/08/new-bluemix-mobile-dashboard/){: new_window}
* [部落格文章：Introducing the next generation of the Bluemix Mobile dashboard](https://ibm.com/blogs/bluemix/2016/10/introducing-the-next-generation-of-the-bluemix-mobile-dashboard/){: new_window}
* [部落格文章：Introducing Bluemix Mobile Code Starters](https://www.ibm.com/blogs/bluemix/2016/10/rapid-dev-with-mobile-code-starters/){: new_window}
* [部落格文章：Bluemix Mobile, Part 1: Creating a Store Catalog application](https://developer.ibm.com/bluemix/2016/07/13/bluemix-mobile-creating-store-catalog-app-part1/){: new_window}
* [部落格文章：Bluemix Mobile, Part 2: Integrating custom Bluemix backend into the Store Catalog app](https://developer.ibm.com/bluemix/2016/07/14/bluemix-mobile-integrating-custom-backend-part2/){: new_window}

## 指導教學與範例
{: #samples}
* [Mobile Backend for Bluemix](https://github.com/ibm-bluemix-mobile-services/mobiledashboard-storecatalog-backend){: new_window}
