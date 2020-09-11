---
title: 기본 Mobility and Security에서 모바일 장치 지우기
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 제공 되는 기본 모바일 및 보안을 사용 하 여 등록 된 장치에서 정보를 제거 합니다.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429953"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>기본 Mobility and Security에서 모바일 장치 지우기

Microsoft 365에 기본 제공 되는 기본 모바일 및 보안을 사용 하 여 조직 정보만 제거 하거나, 공장 초기화를 수행 하 여 모바일 장치에서 모든 정보를 삭제 하 고 공장 설정으로 복원할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

모바일 장치는 중요 한 조직 정보를 저장 하 고 조직의 Microsoft 365 리소스에 대 한 액세스를 제공할 수 있습니다. 조직의 정보를 보호 하려면 다음을 수행 하 여 회사 데이터를 초기화 하거나 제거해 볼 수 있습니다.
    
- **공장 초기화**: 설치 된 응용 프로그램, 사진 및 개인 정보를 포함 하 여 사용자의 모바일 장치에 있는 모든 데이터를 삭제 합니다. 초기화가 완료 되 면 장치가 공장 설정으로 복원 됩니다.
    
- **회사 데이터 제거**: 조직 데이터만 제거 하 고 설치 된 응용 프로그램, 사진 및 개인 정보를 사용자의 모바일 장치에 남겨 둡니다.   

- **장치가 초기화 되 면 (공장 초기화 또는 회사 데이터 제거)** 장치가 관리 되는 장치 목록에서 제거 됩니다.
    
- **자동으로 장치 다시 설정**: 사용자가 특정 횟수 만큼 장치 암호를 입력 하지 못한 후 장치를 자동으로 초기화 하는 기본 이동성 및 보안 정책을 설정할 수 있습니다. 이렇게 하려면 [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies.md)의 단계를 수행 합니다.
    
- 장치를 정리할 때 **사용자 환경을 확인 하려면**   [사용자 및 장치 영향](#whats-the-user-and-device-impact)을 확인 하세요.   

## <a name="wipe-a-mobile-device"></a>모바일 장치 초기화

1.  [Microsoft 365 관리 센터로](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)이동 합니다.
    
2. 검색 필드에 모바일 장치 관리를 입력 하 고 결과 목록에서 **모바일 장치 관리** 를 선택 합니다. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="기본 이동성 및 Secruity 모바일 장치 관리 옵션":::

3. **장치 관리**를 선택 합니다.

4. 초기화 할 장치를 선택합니다.

5. **관리**를 선택 합니다.

6. 원하는 원격 초기화 유형을 선택합니다.

    - 전체 초기화를 수행 하 고 장치를 공장 설정으로 복원 하려면 **공장 초기화**를 선택 합니다.
    - 선택적으로 지우기를 수행 하 고 Microsoft 365 조직 정보만 삭제 하려면 **회사 데이터 제거**를 선택 합니다.
    - 조직에서 디바이스를 제거 하려면 **장치 제거**를 선택 합니다.

7. **예**를 선택하여 확인합니다.

## <a name="how-do-i-know-it-worked"></a>작동 여부는 어떻게 확인 하나요?

관리 되는 장치 목록에 모바일 장치가 더 이상 표시 되지 않습니다.

## <a name="why-would-you-want-to-wipe-a-device"></a>장치를 초기화 하는 이유는 무엇 인가요?

다음과 같은 이유로 장치를 정리 합니다.

- 스마트폰 및 태블릿과 같은 모바일 장치가 항상 모든 기능을 제공 하 고 있습니다. 즉, 사용자가 개인 id 또는 기밀 통신과 같은 중요 한 회사 정보를 보다 쉽게 저장 하 고 이동 중에 액세스할 수 있습니다. 이러한 모바일 장치 중 하나를 분실 하거나 도난당 한 경우 장치를 초기화 하면 조직의 정보가 잘못 된 손에 전달 되는 것을 방지할 수 있습니다.
- 사용자가 기본 Mobility and Security에 등록 되어 있는 개인 장치로 조직을 떠나는 경우, 공장 초기화를 수행 하 여 조직 정보가 해당 사용자와 함께 이동 하지 못하도록 할 수 있습니다.
- 조직에서 사용자에 게 모바일 장치를 제공 하는 경우 시간에서 시간까지 장치를 다시 할당 해야 할 수 있습니다. 장치를 새 사용자에 게 할당 하기 전에 디바이스에서 초기화를 수행 하면 이전 소유자의 중요 한 정보를 삭제 하는 데 도움이 됩니다.

## <a name="whats-the-user-and-device-impact"></a>사용자 및 장치에 미치는 영향은 무엇입니까?

초기화가 모바일 장치로 즉시 전송 되 고 디바이스가 Azure active directory에서 비규격으로 표시 됩니다. 장치를 출고시 기본값으로 다시 설정 하면 모든 데이터가 제거 되지만, 다음 표에서는 회사 데이터를 제거할 때 각 장치 유형에 서 제거 되는 콘텐츠를 설명 합니다.

|**Content  ace**|**iOS 10 이상**|**Android 5 이상**|
|:-----|:-----|:-----|
|Microsoft 365 앱 데이터는 Intune 앱 보호 정책에 의해 보호 되는 장치를 초기화 합니다. 앱이 제거 되지 않습니다. MAM (모바일 응용 프로그램 관리) 정책에 의해 보호 되지 않는 장치의 경우 Outlook 및 OneDrive에서 캐시 된 데이터를 제거 하지 않습니다.<br/>**참고 사항** Intune 앱 보호 정책을 적용 하려면 Intune 라이선스가 있어야 합니다.|예|예|
|기본 이동성 및 장치에 대 한 보안에 의해 적용 되는 정책 설정이 더 이상 적용 되지 않습니다. 사용자가 설정을 변경할 수 있습니다.|예|예|
|기본 이동성 및 보안에 의해 생성 된 전자 메일 프로필이 제거 되 고 장치의 캐시 된 전자 메일이 삭제 됩니다.|예|해당 없음|
>[!NOTE] 
>회사 포털 앱은 iOS 용 앱 스토어 및 Android 장치용 재생 저장소에서 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[기본 이동성 및 보안 설정](set-up.md)