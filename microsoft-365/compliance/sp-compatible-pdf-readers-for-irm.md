---
title: SharePoint-Compatible 권한 관리 서비스를 지원하는 PDF 읽기 권한자 구성
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/5/2017
audience: End User
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- OSU150
- MET150
ms.assetid: dd197d58-5bf6-4d18-b9f8-d16db603fae2
description: IRM(정보 권한 관리)이 Microsoft SharePoint 2013의 IRM으로 보호된 라이브러리에 업로드 및 다운로드된 PDF 문서를 보호하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 70bc0979aca31a735e2c4eb7bfd79e70b2d80b09
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195524"
---
# <a name="sharepoint-compatible-pdf-readers-that-support-microsoft-information-rights-management-services"></a>SharePoint-Compatible 권한 관리 서비스를 지원하는 PDF 읽기 권한자 구성

Microsoft SharePoint 2013에서는 PDF 문서의 IRM(정보 권한 관리) 보호 기능을 제공합니다. 이러한 지원을 통해 사용자는 PDF 문서를 IRM으로 보호된 라이브러리에 업로드할 수 있으며 다운로드 시 IRM을 사용하여 파일을 Microsoft Office 있습니다.
  
소유자가 IRM으로 보호한 라이브러리에서 PDF 파일을 사용하려면 사용자는 다음 PDF 호환 읽기 프로그램 중 하나를 얻어야 합니다.
  
| 운영 체제 | 호환 가능한 독자 | 다운로드 링크 |
|:-----|:-----|:-----|
|Windows Vista  <br/> |Foxit Reader  <br/> NitroPDF  <br/> |[Foxit Reader 다운로드](https://go.microsoft.com/fwlink/?linkid=2139326) <br/> [NitroPDF 다운로드](https://go.microsoft.com/fwlink/?linkid=2139327) <br/> |
|Windows 7  <br/> |Azure Information Protection 앱  <br/> Foxit Reader  <br/> NitroPDF  <br/> Edge Chromium  <br/>|[Azure Information Protection 앱 다운로드](https://go.microsoft.com/fwlink/?linkid=837797) <br/> [Foxit Reader 다운로드](https://go.microsoft.com/fwlink/?linkid=2139326) <br/> [NitroPDF 다운로드](https://go.microsoft.com/fwlink/?linkid=2139327) <br/> [Edge 다운로드 Chromium](https://support.microsoft.com/microsoft-edge/download-the-new-microsoft-edge-based-on-chromium-0f4a3dd7-55df-60f5-739f-00010dba52cf) <br/>|
|Windows 8(클래식 모드)  <br/> |Azure Information Protection 앱  <br/> Foxit Reader  <br/> NitroPDF  <br/> Edge Chromium  <br/>|[Azure Information Protection 앱 다운로드](https://go.microsoft.com/fwlink/?linkid=837797) <br/> [Foxit Reader 다운로드](https://go.microsoft.com/fwlink/?linkid=2139326) <br/> [NitroPDF 다운로드](https://go.microsoft.com/fwlink/?linkid=2139327) <br/> [Edge 다운로드 Chromium](https://support.microsoft.com/microsoft-edge/download-the-new-microsoft-edge-based-on-chromium-0f4a3dd7-55df-60f5-739f-00010dba52cf) <br/> |
|Windows 8.1  <br/> |Azure Information Protection 앱  <br/> Foxit Reader  <br/> NitroPDF  <br/> |[Azure Information Protection 앱 다운로드](https://go.microsoft.com/fwlink/?linkid=837797) <br/> [Foxit Reader 다운로드](https://go.microsoft.com/fwlink/?linkid=2139326) <br/> [NitroPDF 다운로드](https://go.microsoft.com/fwlink/?linkid=2139327) <br/> |
|Windows 10  <br/> |Azure Information Protection 앱  <br/> Foxit Reader  <br/> NitroPDF  <br/> Edge Chromium  <br/> |[Azure Information Protection 앱 다운로드](https://go.microsoft.com/fwlink/?linkid=837797) <br/> [Foxit Reader 다운로드](https://go.microsoft.com/fwlink/?linkid=2139326) <br/> [NitroPDF 다운로드](https://go.microsoft.com/fwlink/?linkid=2139327) <br/> [Edge 다운로드 Chromium](https://support.microsoft.com/microsoft-edge/download-the-new-microsoft-edge-based-on-chromium-0f4a3dd7-55df-60f5-739f-00010dba52cf) <br/> |
|Android  <br/> |Azure Information Protection 앱  <br/> RMS가 있는 Foxit MobilePDF  <br/> |[Azure Information Protection 앱 다운로드](/azure/information-protection/rms-client/protected-pdf-readers#installing-a-protected-pdf-reader-for-mobile-iosandroidc) <br/> [Foxit MobilePDF 구매](https://play.google.com/store/apps/details?id=com.foxit.mobile.pdf.lite) <br/> |
|Windows Phone  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|macOS  <br/> |Edge Chromium  <br/> |[Edge 다운로드 Chromium](https://support.microsoft.com/microsoft-edge/download-the-new-microsoft-edge-based-on-chromium-0f4a3dd7-55df-60f5-739f-00010dba52cf)  <br/> |
|IOS  <br/> |Azure Information Protection 앱  <br/> RMS가 있는 Foxit MobilePDF  <br/> |[Azure Information Protection 앱 다운로드](/azure/information-protection/rms-client/protected-pdf-readers#installing-a-protected-pdf-reader-for-windows-or-mac) <br/> [Foxit MobilePDF 구매](https://play.google.com/store/apps/details?id=com.foxit.mobile.pdf.lite) <br/> |
