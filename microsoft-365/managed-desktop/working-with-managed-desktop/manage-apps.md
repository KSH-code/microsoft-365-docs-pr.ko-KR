---
title: Microsoft Managed Desktop에서 앱 관리
description: Microsoft Managed Desktop 장치에 배포 되는 기간 업무 (lob) 앱 업데이트 방법에 대 한 정보
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ce2765ef2ab176dc5d9a1d41db7e26549b007d79
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285948"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 기간 업무 (lob) 앱 관리

<!--Application management -->

microsoft managed desktop에 등록 microsoft managed desktop 장치에 배포 된 앱에 대 한 앱 업데이트를 관리 하는 방법에는 몇 가지가 있습니다. Microsoft Managed Desktop portal 또는 Intune에서 앱 업데이트를 만들 수 있습니다. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 기간 업무 (lob) 앱 업데이트

**Microsoft Managed Desktop portal에서 기간 업무 (lob) 앱을 업데이트 하려면**
1. [Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.
2. **인벤토리에서** **앱**을 선택 합니다.  
3. 업데이트할 앱을 선택 하 고 **편집**을 선택 합니다.
4. **관리**에서 **속성**을 선택 합니다. 
5. **앱 패키지 파일**을 클릭 한 다음 새 앱 패키지 파일을 찾아서 업로드 합니다.
6. **앱 패키지 파일**을 선택 합니다.
7. 폴더 아이콘을 선택 하 고 업데이트 된 앱 파일의 위치를 찾습니다. **열기**를 선택합니다. 앱 정보가 패키지 정보로 업데이트 됩니다.
8. **앱 버전이** 업데이트 된 앱 패키지를 반영 하는지 확인 합니다. 

업데이트 된 앱이 사용자의 장치에 배포 됩니다.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Intune에서 기간 업무 (lob) 앱 업데이트

**Intune에서 기간 업무 (lob) 앱을 업데이트 하려면**
1. [Azure 포털](https://azure.portal.com)에 로그인 합니다.
2. **모든 서비스** > **Intune**을 선택 합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **클라이언트 앱 > 앱**을 선택 합니다.
4. 앱 목록에서 앱을 찾아 선택 합니다.
5. **개요** 블레이드에서 **속성**을 선택 합니다.
6. **앱 패키지 파일**을 선택 합니다.
7. 폴더 아이콘을 선택 하 고 업데이트 된 앱 파일의 위치를 찾습니다. **열기**를 선택합니다. 앱 정보가 패키지 정보로 업데이트 됩니다.
8. **앱 버전이** 업데이트 된 앱 패키지를 반영 하는지 확인 합니다.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>앱을 이전 버전으로 롤백

새 버전의 앱이 배포 될 때 오류가 발견 되는 경우 이전 버전으로 롤백할 수 있습니다. 여기에 설명 된 프로세스는 유형이 **Windows MSI lob (기간 업무) 앱** 또는 **windows app (Win 32)-preview** 로 나열 된 앱에 대 한 것입니다.

**기간 업무 (lob) 앱을 이전 버전으로 롤백하는 방법**

1. [Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.
2. **인벤토리에서** **앱**을 선택 합니다.  
3. 롤백하는 데 필요한 앱을 선택 하 고 **편집**을 선택 합니다.
4. **관리**에서 **속성**을 선택 합니다. 
    - **Windows MSI lob (기간 업무) 앱** 앱의 경우 **앱 정보**를 선택 하 고 **응용 프로그램 버전 무시**에서 **예**를 선택 합니다.
    - **Windows 앱 (Win 32)-미리 보기** 앱에서 **앱 정보**를 선택 하 고 **검색 규칙**을 선택한 다음 **추가**를 선택 합니다. 
    msi 규칙이 있는 경우 **msi 제품 버전 확인** 이 **아니요로**설정 되어 있는지 확인 합니다.
5. [이전 버전의 앱 원본 파일](../get-started/deploy-apps.md) 을 Microsoft Managed Desktop administration portal에 업로드 합니다.  

