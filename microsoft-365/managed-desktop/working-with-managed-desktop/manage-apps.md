---
title: 앱에서 앱 Microsoft Managed Desktop
description: 디바이스에 배포된 업무용 앱을 업데이트하는 Microsoft Managed Desktop 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215172"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 업무용 앱 관리

<!--Application management -->

앱에 온보드하고 앱 디바이스에 배포한 앱에 대한 앱 업데이트를 Microsoft Managed Desktop 두 가지 Microsoft Managed Desktop 있습니다. 포털 또는 Intune에서 앱을 Microsoft Managed Desktop 수 있습니다. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>2016년 12월에 업무용 앱을 Microsoft Managed Desktop

**포털에서 업무용 앱을 Microsoft Managed Desktop**
1. 관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal)
2. **인벤토리에서** 앱을 **선택합니다.**  
3. 업데이트할 앱을 선택하고 편집 을 **선택합니다.**
4. **관리에서** 속성을 **선택합니다.** 
5. 앱 **패키지 파일을 클릭한** 다음 새 앱 패키지 파일을 업로드합니다.
6. 앱 **패키지 파일을 선택합니다.**
7. 폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다. **열기** 를 선택합니다. 앱 정보가 패키지 정보로 업데이트됩니다.
8. 앱 **버전이 업데이트된** 앱 패키지를 반영하는지 확인 

업데이트된 앱이 사용자의 디바이스에 배포됩니다.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Intune에서 업무용 앱 업데이트

**Intune에서 업무용 앱을 업데이트하는 경우**
1. [Azure Portal에 로그인합니다.](https://portal.azure.com)
2. 모든 **서비스**  >  **Intune을 선택합니다.** Intune은 **모니터링 + 관리 섹션에** 있습니다.
3. 클라이언트 **앱 및 > 선택합니다.**
4. 앱 목록에서 앱을 찾아 선택합니다.
5. 개요 **블레이드에서** 속성을 **선택합니다.**
6. 앱 **패키지 파일을 선택합니다.**
7. 폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다. **열기** 를 선택합니다. 앱 정보가 패키지 정보로 업데이트됩니다.
8. 앱 **버전이 업데이트된** 앱 패키지를 반영하는지 확인

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>이전 버전으로 앱 롤백

새 버전의 앱을 배포할 때 오류가 발견되면 이전 버전으로 롤백할 수 있습니다. 여기에 설명된 프로세스는 **유형이 MSI** 업무용 앱 또는 Windows 앱(Win **32)** - 미리 보기로 Windows 앱에 대한 프로세스입니다.

**업무용 앱을 이전 버전으로 롤백**

1. 관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal)
2. **인벤토리에서** 앱을 **선택합니다.**  
3. 롤백해야 하는 앱을 선택하고 편집 을 **선택합니다.**
4. **관리에서** 속성을 **선택합니다.** 
    - MSI **Windows** 앱 앱의 경우 앱 정보를 선택하고 앱 버전 무시에서 **예를** **선택합니다.**
    - 앱 **Windows (Win 32) -** 앱 미리 보기, 앱 **정보,** 검색 규칙, 추가를 **선택합니다.** 
    MSI 규칙이 있는 경우 **MSI** 제품 버전 확인이 아니요로 설정되어 있는지 **확인해야 합니다.**
5. [업로드 이전](../get-started/deploy-apps.md) 버전의 앱 원본 파일을 관리 포털에 Microsoft Managed Desktop 수 있습니다.  

