---
title: 장치에 대 한 라이선스 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 장치에 사용 하기 위해 그룹에 라이선스를 할당 하는 방법을 알아봅니다.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826282"
---
# <a name="manage-licenses-for-devices"></a>장치에 대 한 라이선스 관리

교육용 (장치) 용 office 365 ProPlus (장치) 또는 Office 365 ProPlus가 있는 경우 Azure AD 그룹을 사용 하 여 장치에 라이선스를 할당할 수 있습니다. 장치에 라이선스가 있으면 해당 장치를 사용 하는 모든 사용자가 Office 365를 사용할 수 있습니다. 예를 들어 조직의 사용자가 사용 하는 20 개의 랩톱과 태블릿이 있는 경우를 가정해 보겠습니다. 각 장치에 라이선스를 할당 하면 장치 중 하나에 로그인 하는 각 사용자는 자신의 라이선스 없이도 Office 365을 사용 합니다.

> [!IMPORTANT]
> Office 365 ProPlus에 대 한 장치 기반 라이선스는 일부 주석 및 일부 교육 고객에 대 한 추가 기능 라이선스로만 사용할 수 있습니다. 상업용 고객의 경우 라이선스는 *Office 365 ProPlus (장치)* 이며 엔터프라이즈 계약/엔터프라이즈 계약 구독을 통해서만 사용할 수 있습니다. 교육 고객의 경우 라이선스는 *교육을 위한 Office 365 ProPlus (장치)* 이며 EES (교육 솔루션) 등록을 통해서만 사용할 수 있습니다. 자세한 내용은 [교육 사용 가능 여부](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)에 대 한 블로그 게시물을 참조 하세요. 상업용 사용 가능 여부는 Microsoft 계정 담당자에 게 문의 하세요.

시작 하려면 Azure Active Directory 관리 센터에서 그룹을 만든 다음이 그룹에 장치를 할당 합니다. 장치 요구 사항, 사용할 수 있는 그룹 유형 및 장치 라이선스를 사용 하도록 Office 365 ProPlus를 구성 하는 방법에 대 한 자세한 내용은 [office 365 proplus에 대 한 장치 기반 라이선스](https://go.microsoft.com/fwlink/p/?linkid=2094216)를 참조 하세요.

> [!IMPORTANT]
> 이 문서의 작업을 완료 하려면 전역 관리자 여야 합니다.

## <a name="assign-licenses-to-devices"></a>장치에 라이선스 할당

그룹에 라이선스를 할당 하는 경우 그룹 내의 모든 장치에 라이선스를 할당 합니다. 하나의 구독을 단일 그룹에만 할당할 수 있습니다.

1. Microsoft 365 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.
2. **라이선스** 페이지에서 교육용 (장치) 또는 **office ProPlus (장치)** **용 office 365 ProPlus** 를 선택 합니다.
3. 다음 페이지에서 구독을 선택 하 고 **라이선스 할당**을 선택 합니다.
4. **그룹에 라이선스 할당** 창에서 그룹 이름을 입력 하 고 결과에서 선택 하 여 목록에 추가 합니다.
5. **할당**을 선택한 다음 **닫기를**선택 합니다.

## <a name="unassign-licenses-from-devices"></a>장치에서 라이선스 할당 해제

그룹의 라이선스 할당을 취소 하는 경우 그룹 내의 모든 장치에서 라이선스를 제거 합니다. 모든 앱 및 연결 된 데이터는 읽기 전용입니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.
2. **라이선스** 페이지에서 교육용 (장치) 또는 **office ProPlus (장치)** **용 office 365 ProPlus** 를 선택 합니다.
3. 다음 페이지에서 구독을 선택 하 고 **기타 작업**을 선택한 다음 **라이선스 할당**해제를 선택 합니다.
4. **라이선스 할당** 해제 대화 상자에서 **할당**해제를 선택 합니다.