---
title: 장치에 대한 라이선스 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 디바이스에서 사용할 수 있는 그룹에 라이선스를 할당하는 방법을 학습합니다.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638186"
---
# <a name="manage-licenses-for-devices"></a>장치에 대한 라이선스 관리

엔터프라이즈용 Microsoft 365 앱(장치) 또는 교육용 Microsoft 365 앱(장치)이 있는 경우 Azure AD 그룹을 사용하여 디바이스에 라이선스를 할당할 수 있습니다. 디바이스에 라이선스가 있는 경우 해당 장치를 사용하는 모든 사용자가 엔터프라이즈용 Microsoft 365 앱(이전의 Office 365 ProPlus)을 사용할 수 있습니다. 예를 들어 조직의 사람들이 사용하는 랩톱과 태블릿이 20개라고 합니다. 각 장치에 라이선스를 할당하면 장치 중 하나에 로그인하는 각 사용자가 자체 라이선스 없이 엔터프라이즈용 Microsoft 365 앱을 사용합니다.

> [!IMPORTANT]
> 엔터프라이즈용 Microsoft 365 앱에 대한 장치 기반 라이선싱은 일부 상업 고객 및 일부 교육 고객을 위한 추가 기능 라이선스로만 사용할 수 있습니다. 상용 고객의 경우 라이선스는 *엔터프라이즈용 Microsoft 365* 앱(장치)으로, 기업계약/기업계약 구독을 통해서만 사용할 수 있습니다. 교육 고객의 경우 라이선스는 *교육용 Microsoft 365* 앱(장치)으로, EES(Education 솔루션 등록)를 통해서만 사용할 수 있습니다. 자세한 내용은 교육 가용성에 대한 블로그 [게시물을 참조하세요.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) 상업적 가용성을 확인하려면 Microsoft 계정 담당자에게 문의하세요.

먼저 Azure Active Directory 관리 센터에서 그룹을 만든 다음 그룹에 장치를 할당합니다. 장치 요구 사항, 사용할 수 있는 그룹 유형 및 장치 라이선스를 사용하도록 엔터프라이즈용 Microsoft 365 앱을 구성하는 방법을 포함하여 장치 라이선스에 대한 자세한 내용은 [엔터프라이즈용 Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2094216)앱에 대한 장치 기반 라이선싱을 참조하세요.

> [!IMPORTANT]
> 이 문서의 작업을 완료하려면 전역 관리자 되어야 합니다.

## <a name="assign-licenses-to-devices"></a>장치에 라이선스 할당

그룹에 라이선스를 할당할 때 그룹 내의 모든 장치에 라이선스를 할당합니다. 단일 그룹에 구독을 하나만 할당할 수 있습니다.

1. Microsoft 365 관리 센터에서 청구 라이선스  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.
2. 라이선스 **페이지에서** **교육용 Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)을 선택합니다.**
3. 다음 페이지에서 구독을 선택한 다음 라이선스 **할당을 선택합니다.**
4. 그룹 **창에 라이선스** 할당에서 그룹 이름을 입력하기 시작한 다음 결과에서 선택한 후 목록에 추가합니다.
5. Choose **Assign,** then choose **Close**.

## <a name="unassign-licenses-from-devices"></a>장치에서 라이선스를 배포하지 않습니다.

그룹에서 라이선스를 배포할 때 그룹 내의 모든 장치에서 라이선스를 제거합니다. 그러면 모든 앱과 관련 데이터가 읽기 전용입니다.

1. 관리 센터에서 청구 라이선스   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.
2. 라이선스 **페이지에서** **교육용 Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)을 선택합니다.**
3. On the next page, choose a subscription, choose **More actions,** then choose **Unassign licenses.**
4. 라이선스 배포 **안함** 대화 상자에서 사용 안 을 **선택합니다.**