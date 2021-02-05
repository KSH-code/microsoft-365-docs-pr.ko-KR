---
title: 구독에 대한 저장소 공간 추가
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 구독에서 파일 저장소를 추가하고 줄이는 방법을 학습합니다. 추가 파일 저장소를 사용하면 SharePoint Online 및 OneDrive에 더 많은 콘텐츠를 저장할 수 있습니다.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114910"
---
# <a name="add-storage-space-for-your-subscription"></a>구독에 대한 저장소 공간 추가

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다. 사용 가능한 추가 기능 목록에 **Office 365 추가** 파일 저장소가 없는 경우 요금제가 자격이 없는 것입니다. 자세한 내용은 내 계획이 [적합한지 여부](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> 볼륨 라이선스 또는 CSP를 통해 구독을 구입한 경우 Microsoft에서 직접 조직의 **Office 365 추가** 파일 저장소를 구입할 수 없습니다. 담당자나 파트너에게 도움을 문의하세요.

## <a name="before-you-begin"></a>시작하기 전에

이 문서의 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다. 자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="view-available-storage"></a>사용 가능한 저장소 보기

::: moniker range="o365-worldwide"

1. SharePoint 관리 센터에서 활성 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> 사이트 페이지로 이동한 다음 조직에 [](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) 대한 관리자 권한이 있는 계정으로 로그인합니다.

2. 페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다. 조직에서 Office 365에서 Multi-Geo를 구성한 경우 표시줄에는 모든 지리적 위치에서 사용되는 저장소의 양도 표시됩니다.

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.

::: moniker-end

::: moniker range="o365-germany"

1. 전역 또는 SharePoint 관리자로 로그인한 다음 관리 타일을 선택하여 관리 https://portal.office.de 센터를 하세요. 페이지에 액세스할 수 있는 권한이 없는 메시지가 표시면 조직에 Microsoft 365 관리자 권한이 없는 것입니다.

2. 왼쪽 창의 관리 센터에서 **SharePoint를 선택합니다.** 기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기** 를 선택하여 새 SharePoint 관리 센터를 엽니다.

3. 새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트** 를 선택합니다.

4. 페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 전역 또는 SharePoint 관리자로 로그인한 다음 관리 타일을 선택하여 관리 https://login.partner.microsoftonline.cn/ 센터를 하세요. 페이지에 액세스할 수 있는 권한이 없는 메시지가 표시된 경우 조직에 Microsoft 365 관리자 권한이 없는 것입니다.

2. 왼쪽 창의 관리 센터에서 **SharePoint를 선택합니다.** 기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기** 를 선택하여 새 SharePoint 관리 센터를 엽니다.

3. 새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트** 를 선택합니다.

4. 페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.  

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.

::: moniker-end

사용 중인 저장소의 용량을 확인한 후에는 구독에 대해 저장소 공간을 추가 또는 제거할 수 있습니다. 저장소 공간을 추가하는 데 드는 비용에 대해 자세한 내용은 이 문서의 단계를 따르고 구매하기 전에 가격 정보를 검토하세요.
  
사이트 모음 저장 용량 제한 설정에 대한 자세한 내용은 사이트 모음 저장 용량 제한 [관리를 참조하십시오.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)
  
## <a name="add-storage-to-your-subscription"></a>구독에 저장소 추가

구독에 대한 추가 저장소를 아직 구매하지 않은 경우 이 작업을 할 수 있습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 대금  청구 서비스 페이지로 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank"></a> 이동합니다.
2. 서비스 구매 페이지의 맨 **아래에서** 추가 **기능을 선택합니다.**
3. **Office 365 추가 파일 저장소를 선택합니다.**
4. Office **365 추가** 파일 저장소 페이지에 표시되는 경우 기본 구독을 선택한 다음 추가할 저장소의 기가바이트 수를 입력합니다.
5. 지금 **체크 아웃을 선택합니다.**
6. 어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**
7. 주문 **완료 페이지에서** 합계를 확인하십시오. 변경해야 하는 경우 순서 **편집을 선택합니다.** 주문에 신용 검사가 필요한 경우 확인란을 선택합니다. 완료되면 관리 홈으로 이동  \> **순서를 선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 청구 구독  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">페이지로</a> 이동합니다.  

2. 구독 **페이지에서** 저장소 공간을 추가할 구독을 선택한 다음 추가 **기능을 선택합니다.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > 추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.
  
3. 추가 **기능 구입을 선택합니다.**

    ![관리 센터의 구독 페이지에서 추가 기능 링크를 구입합니다.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. 서비스 **구매 페이지에서** **Office 365** 추가 파일 저장소를 마우스로 마우스로 클릭하거나 탭한 다음 지금 **구입을 선택합니다.**
  
5. 필요한 사용자 라이선스 수를 입력하고 표시되는 경우 기본 구독을 선택합니다. 지금 **체크 아웃을 선택합니다.**
  
6. 어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**

7. 주문 **완료 페이지에서** **주문을 선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.

2. 구독 **페이지에서** 저장소 공간을 추가할 구독을 선택한 다음 추가 **기능을 선택합니다.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > 추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.
  
3. 추가 **기능 구입을 선택합니다.**

    ![관리 센터의 구독 페이지에서 추가 기능 링크를 구입합니다.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. 서비스 **구매 페이지에서** **Office 365** 추가 파일 저장소를 마우스로 마우스로 클릭하거나 탭한 다음 지금 **구입을 선택합니다.**
  
5. 필요한 사용자 라이선스 수를 입력하고 표시되는 경우 기본 구독을 선택합니다. 지금 **체크 아웃을 선택합니다.**
  
6. 어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**

7. 주문 **완료 페이지에서** **주문을 선택합니다.**

::: moniker-end

## <a name="increase-or-decrease-storage"></a>저장소 확대 또는 축소

**Office 365** 추가 파일 저장소 추가 기능을 통해 추가 파일 저장소를 이미 구입한 경우 다음 단계를 사용하여 구독에 대한 추가 저장소 공간을 늘리거나 줄이면 됩니다. 저장소를 1기가바이트까지 줄일 수 있습니다. 추가 저장소 공간을 모두 제거하려면 고객 [지원에 문의합니다.](../admin/contact-support-for-business-products.md)

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.
2. 제품 **탭에서** **Office 365** 추가 파일 저장소 추가 기능을 포함하는 구독을 선택합니다.
3. 제품 세부 정보 페이지의 추가  기능 섹션에서 추가 기능 관리 **를 선택합니다.**
4. 추가 기능 관리 **창의** 추가 기능  목록에서 Office **365 추가 파일 저장소를 선택합니다.**
5. 수량 **입력란에** 구독에 사용할 저장소 공간의 GB 수를 입력합니다.
6. **저장** 을 선택합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.

2. 구독 **페이지에서** 추가 **기능을 선택합니다.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > 추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.
  
3. **Office 365 추가 파일 저장소에서** 수량 **변경을 선택합니다.**

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 오른쪽 창에 필요한 총 기가바이트 수를 입력한 다음 제출을 **선택합니다.**

    예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100** 을 입력할 수 있습니다.

5. **닫기** 를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.

2. 구독 **페이지에서** 추가 **기능을 선택합니다.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > 추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.
  
3. **Office 365 추가 파일 저장소에서** 수량 **변경을 선택합니다.**

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 오른쪽 창에 필요한 총 기가바이트 수를 입력한 다음 제출을 **선택합니다.**

    예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100** 을 입력할 수 있습니다.

5. **닫기** 를 선택합니다.

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?

Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.
  
- Office 365 Enterprise E1

- Office 365 Enterprise E2

- Office 365 Enterprise E3

- Office 365 Enterprise E4

- Office 365 Enterprise E5

- SharePoint 계획 1을 통해 웹용 Office

- SharePoint 요금제 2를 통해 웹용 Office

- SharePoint Online 요금제 1

- SharePoint Online 요금제 2

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> GCC, GCC High 및 DOD 계획에도 Office 365 추가 파일 저장소를 사용할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[사이트 저장 용량 제한](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) 관리(문서)\
[OneDrive 사용자에](https://docs.microsoft.com/onedrive/set-default-storage-space)대한 기본 저장소 공간 설정(문서)
