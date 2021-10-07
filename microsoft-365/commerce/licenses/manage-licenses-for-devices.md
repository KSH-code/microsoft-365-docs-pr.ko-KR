---
title: 장치에 대한 라이선스 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
description: 디바이스에서 사용할 수 있는 그룹에 라이선스를 할당하는 방법을 배워야 합니다.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 08/27/2021
ms.openlocfilehash: 674874a6e27afa6e08ca4ee77de4ecac51796de8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179634"
---
# <a name="manage-licenses-for-devices"></a>장치에 대한 라이선스 관리

디바이스(엔터프라이즈용 Microsoft 365 앱) 또는 Microsoft 365 앱(장치)가 있는 경우 Azure AD 그룹을 사용하여 디바이스에 라이선스를 할당할 수 있습니다. 디바이스에 라이선스가 있는 경우 해당 장치를 사용하는 모든 사용자가 라이선스를 사용할 엔터프라이즈용 Microsoft 365 앱(Office 365 ProPlus). 예를 들어 조직의 사람들이 사용하는 랩톱과 태블릿이 20개라고 합니다. 각 장치에 라이선스를 할당하면 장치 중 하나에 로그인하는 각 사용자가 고유한 엔터프라이즈용 Microsoft 365 앱 필요 없이 라이선스를 사용합니다.

> [!IMPORTANT]
> 디바이스 기반 라이선싱은 엔터프라이즈용 Microsoft 365 앱 일부 상용 고객 및 일부 교육 고객을 위한 추가 기능 라이선스로만 사용할 수 있습니다. 상업적 고객의 경우  라이선스는 엔터프라이즈용 Microsoft 365 앱(장치)으로, 기업계약/기업계약 구독을 통해서만 사용할 수 있습니다. 교육 고객의 경우 라이선스는 *Microsoft 365 앱(디바이스)에* 등록되어 있으며 EES(Education 솔루션 등록)를 통해서만 사용할 수 있습니다. 자세한 내용은 교육 가용성에 대한 블로그 [게시물을 참조하세요.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education) 상업적 가용성을 확인하려면 Microsoft 계정 담당자에게 문의하세요.

시작하려면 Azure Active Directory 관리 센터에서 그룹을 만든 다음 그룹에 장치를 할당합니다. 장치 요구 사항, 사용할 수 있는 그룹 유형 및 장치 라이선스를 사용하도록 장치 라이선스를 엔터프라이즈용 Microsoft 365 앱 방법을 포함하여 장치 라이선스에 대한 자세한 내용은 장치 기반 라이선싱을 [엔터프라이즈용 Microsoft 365 앱.](/deployoffice/device-based-licensing)

> [!IMPORTANT]
> 이 문서의 작업을 완료하려면 전역 관리자 되어야 합니다.

## <a name="assign-licenses-to-devices"></a>장치에 라이선스 할당

그룹에 라이선스를 할당할 때 그룹 내의 모든 장치에 라이선스를 할당합니다. 단일 그룹에 구독을 하나만 할당할 수 있습니다.

1. In the Microsoft 365 관리 센터, go to the **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.
2. 라이선스 **페이지에서** 교육용 **Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)를 선택합니다.**
3. On the next page, choose a subscription, then choose **Assign licenses**.
4. 그룹에 **라이선스** 할당 창에서 그룹 이름을 입력하기 시작한 다음 결과에서 선택한 후 목록에 추가합니다.
5. 할당 **을** 선택한 다음 **닫기 를 선택.**

## <a name="unassign-licenses-from-devices"></a>장치에서 라이선스를 배포하지 않습니다.

그룹에서 라이선스를 배포를 제거하면 그룹 내의 모든 장치에서 라이선스가 제거됩니다. 그러면 모든 앱과 관련 데이터가 읽기 전용입니다.

1. 관리 센터에서 청구 라이선스   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.
2. 라이선스 **페이지에서** 교육용 **Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)를 선택합니다.**
3. 다음 페이지에서 구독을 선택하고 세 개의 점(추가 작업)을 선택한 다음 라이선스 배포 **취소를 선택합니다.**
4. 라이선스의 사용 허가 **안 함 대화** 상자에서 **Unassign 을 선택합니다.**
