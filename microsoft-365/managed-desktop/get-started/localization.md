---
title: 사용자 환경 현지화
description: 사용자를 위해 디바이스를 지역화하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023264"
---
# <a name="localize-the-user-experience"></a>사용자 환경 현지화

Microsoft Managed Desktop 장치 사용자는 설치 프로세스("첫 실행 경험") 또는 그 이후에 원하는 언어를 선택할 수 있습니다.

## <a name="during-setup-the-out-of-box-experience"></a>설치 중("첫 실행 경험")

설치를 완료하는 동안 사용자는 원하는 언어를 선택할 수 있습니다. 이 선택은 다음 특성에 영향을 미치게 됩니다.

- Windows 10 언어 기능:
    - 표시 언어
    - 키보드 언어
    - 언어 관련 요구 시 기능

- 엔터프라이즈용 Microsoft 365 앱 언어 기능:
    - 표시 언어
    - 교정 및 제작 도구

> [!NOTE]
> 사용자는 설치 프로세스 중에 언어를 선택하여 언어 관련 기능만 받을 수 있습니다.

## <a name="after-completing-setup"></a>설치를 완료한 후

사용자는 설치 프로세스가 완료된 후 언제든지 Windows 10 및 엔터프라이즈용 Microsoft 365 앱에 대해 원하는 언어를 선택할 수 있습니다. 특히 다음 사항에 유의합니다.

- Windows 10 언어 기능:
    - 표시 언어
    - 키보드 언어

- 엔터프라이즈용 Microsoft 365 앱 언어 기능:
    - 표시 언어
    - 교정 및 제작 도구

사용자가 설치할 [](#supported-languages) 수 있는 엔터프라이즈용 Microsoft 365 앱의 지원되는 언어를 만들 수 있도록 최신 **Workplace-Office-Language_Packs** 그룹에 사용자를 추가합니다. 언어는 Intune 회사 포털에서 사용할 수 있습니다.


## <a name="supported-languages"></a>지원되는 언어

새 장치의 경우 제조업체에서 필요한 언어가 포함된 장치 이미지를 제공해야 합니다. 제조업체 이미지에 지원되는 언어 목록에 제공된 언어가 다른 언어가 포함되어 있는 경우 서비스에서 여전히 지원됩니다.

기존 장치를 다시 사용하려면 Microsoft 계정 담당자와 함께 적절한 이미지를 얻어야 할 수 있습니다. 자세한 내용은 장치 이미지를 [참조하세요.](../service-description/device-images.md)

Microsoft Managed [Desktop에서](../service-description/device-images.md#universal-image) 제공하는 유니버설 이미지에는 다음 언어와 Windows 10용이 포함되어 있습니다.

- 아랍어
- 불가리아어
- Chinese Simplified
- Chinese Traditional
- 크로아티아어
- 체코어
- 덴마크어  
- 네덜란드어  
- 영어(미국, GB, AU, CA, IN)
- 에스토니아어
- 핀란드어 
- 프랑스어(프랑스, 캐나다)
- 독일어
- 그리스어
- 히브리어
- 헝가리어
- 인도네시아어
- 이탈리아어
- 일본어
- 한국어
- 라트비아어
- 리투아니아어
- 노르웨이어(복말)
- 폴란드어
- 포르투갈어(브라질)
- 포르투갈어(포르투갈)
- 루마니아어
- 러시아어 
- 세르비아어(라틴 문자 알파벳)
- 슬로바키아어
- 슬로베니아어
- 스페인어(스페인, 멕시코)
- 스웨덴어
- 태국어
- 터키어
- 우크라이나어
- 베트남어

엔터프라이즈용 Microsoft 365 앱은 약간 다른 목록을 지원할 수 있습니다.

여기에 나열된 언어가 다른 언어가 필요한 경우 [](../working-with-managed-desktop/admin-support.md) 관리 포털을 사용하여 지원 요청을 [제출합니다.](access-admin-portal.md)

## <a name="languages-for-support-and-operations"></a>지원 및 운영 언어

### <a name="user-support"></a>사용자 지원
Microsoft Managed Desktop은 영어로만 지원을 제공합니다. 사용자가 도움말 보기 앱에서 다른 언어를 선택하면 Microsoft Managed Desktop에서 직접 지원하지 않고 일반 Microsoft 지원 채널에서 지원을 받을 수 있습니다. 자세한 내용은 [사용자에 대한 도움말 보기를 참조하세요.](../working-with-managed-desktop/end-user-support.md)

사용자가 다른 언어로 지원을 필요로 하는 경우 Microsoft가 아닌 지원 원본이나 조직에서 지원을 제공해야 합니다.

### <a name="admin-support-and-operations"></a>관리자 지원 및 운영
Microsoft Managed Desktop은 영어로만 관리자 지원을 제공합니다. 여기에는 관리 포털 및 Microsoft Managed Desktop 작업과의 모든 통신이 포함됩니다. 달리 지정하지 않는 한 모든 관리자 관련 상호 작용 및 인터페이스가 영어로 제공된다고 가정해야 합니다.


