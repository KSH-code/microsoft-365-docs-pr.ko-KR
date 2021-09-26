---
title: 기본 모바일 및 보안에서 장치 보안 정책 만들기
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 기본 모바일 및 보안을 사용하여 조직 정보를 보호하는 장치 정책을 만들 수 있습니다.
ms.openlocfilehash: 06d377e86913cbacd781241d75765e6b6cc63b8b
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775183"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>기본 모바일 및 보안에서 장치 보안 정책 만들기

기본 Mobility and Security를 사용하여 조직에 대한 조직 정보를 무단 액세스로부터 보호하는 Microsoft 365 수 있습니다. 장치의 사용자에게 해당 Microsoft 365 라이선스가 있으며 기본 모바일 및 보안에 장치를 등록한 조직의 모든 모바일 장치에 정책을 적용할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에 다음의 조건을 만족해야 합니다.

> [!IMPORTANT]
> 모바일 장치 정책을 만들기 전에 기본 모바일 및 보안을 활성화하고 설정해야 합니다. 자세한 내용은 Overview of Basic Mobility and Security를 참조하세요.

- 기본 모바일 및 보안에서 지원하는 장치, 모바일 장치 앱 및 보안 설정에 대해 자세히 알아보습니다. [Basic Mobility and Security의 기능을 참조합니다.](capabilities.md)
- 정책을 배포할 Microsoft 365 사용자에 대한 액세스가 차단되지 않을 수 있는 사용자에 대한 보안 그룹을 Microsoft 365. 조직에 새 정책을 배포하기 전에 소수의 사용자에게 배포하여 정책을 테스트하는 것이 좋습니다. 정책을 테스트할 수 있는 사용자 또는 소수의 사용자만 포함된 보안 Microsoft 365 만들고 사용할 수 있습니다. 보안 그룹에 대한 자세한 내용은 보안 그룹 [만들기, 편집 또는 삭제를 참조합니다.](../email/create-edit-or-delete-a-security-group.md)
- 기본 이동성 및 보안 정책을 만들고 배포하려면 Microsoft 365 전역 Microsoft 365 합니다. 자세한 내용은 보안 및 준수 [센터의 & 참조하세요.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- 정책을 배포하기 전에 조직에 기본 모바일 및 보안에서 장치 등록이 미칠 수 있는 영향을 알 수 있습니다. 정책을 설정하는 방법에 따라 등록된 디바이스에 설치된 응용 프로그램Microsoft 365 사진 및 개인 정보를 포함하여 준수하지 않는 장치가 장치 및 데이터에 액세스하지 못하게 차단할 수 있으며 데이터를 삭제할 수 있습니다.

> [!NOTE]
> 기본 모바일 및 보안 for Microsoft 365 Business Standard 정책 및 액세스 규칙은 Exchange ActiveSync 관리 센터에서 만든 모바일 Exchange ActiveSync 정책 및 장치 액세스 규칙을 Exchange 합니다. 기본 모바일 및 보안 for Microsoft 365 Business Standard 장치에 등록된 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙은 무시됩니다. 자세한 내용은 Exchange ActiveSync 에서 Exchange ActiveSync [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>1단계: 장치 정책을 만들고 테스트 그룹에 배포

시작하기 전에 기본 Mobility and Security를 활성화하고 설정해야 합니다. 자세한 내용은 [Overview of Basic Mobility and Security를 참조하십시오.](overview.md)

1. 브라우저에서 를 <https://protection.office.com/devicev2> 입력합니다.

2. **정책 만들기** 를 선택합니다.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 모바일 및 보안 정책 설정":::

3. 정책 **설정 페이지에서** 조직의 모바일 장치에 적용할 요구 사항을 지정합니다.

4. **전자 메일 프로필** 관리 필요: 사용하도록 설정하면 기본 이동성 및 보안으로 관리되는 전자 메일 프로필이 없는 장치는 규격이 아닌 것으로 간주됩니다. 디바이스의 대상이 올바르게 지정되지 않은 경우 또는 사용자가 디바이스에서 전자 메일 계정을 수동으로 설정한 경우 디바이스에 관리되는 전자 메일 프로필을 사용할 수 없습니다. 사용 안  하도록 설정(기본값)으로 두면 이 설정이 준수 또는 비준수로 평가되지 않습니다. 이 옵션을 선택할 때 사용자가 규정 준수를 받을 수 있는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 을 참조하세요.](/intune-user-help/existing-company-email-account-found)

5. 지금 **이 정책을** 적용하고 싶나요? 페이지에서 이 정책을 적용할 그룹을 선택합니다.

6. 이 **정책 만들기 를 선택합니다.**

정책은 다음에 모바일 장치를 사용하여 로그인할 때 각 Microsoft 365 푸시됩니다. 사용자가 이전의 모바일 장치에 정책을 적용하지 않은 경우 정책을 배포한 후 기본 모바일 및 보안을 등록하고 활성화하는 단계가 포함된 알림이 장치에 표시됩니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md) Intune 서비스에서 호스팅하는 기본 모바일 및 보안에 등록할 때까지 전자 메일, OneDrive 및 기타 서비스에 대한 액세스가 제한됩니다. Intune 회사 포털 앱을 사용하여 등록을 완료한 후 서비스를 사용할 수 있으며 정책이 장치에 적용됩니다.

## <a name="step-2-verify-that-your-policy-works"></a>2단계: 정책이 작동하는지 확인

장치 정책을 만든 후 정책이 조직에 배포하기 전에 예상한 것만큼 작동하는지 확인합니다.

1. 브라우저에서 를 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 입력합니다.
2. 관리되는 **장치 목록 보기를 선택합니다.**
3. 정책이 적용된 사용자 장치의 상태를 검사합니다. 장치 **상태를** **관리하려는 경우**
4. 장치를 선택한 후 초기화 또는 관리 단추에서 회사 데이터  제거를 클릭하여  디바이스에서 전체 또는 선택적 지우기를 할 수도 있습니다.  자세한 내용은 [모바일 장치에서 모바일 장치 지우기)를 Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>3단계: 조직에 정책 배포

장치 정책을 만들어 예상대로 작동하는지 확인한 후 조직에 배포합니다.

1. 브라우저 유형에서: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. 배포할 정책을 선택하고 적용된  그룹 옆에 **있는 편집을 선택합니다.**
3. 추가할 그룹을 검색하고 선택을 **클릭합니다.**
4. 닫기 **및** **변경 설정을 선택합니다.**
5. 정책 **닫기** **및 편집을 선택합니다.**

정책은 각 사용자의 모바일 장치로 푸시됩니다. 다음에 모바일 장치에서 모바일 장치에 로그인할 때 정책이 Microsoft 365 적용됩니다. 사용자가 모바일 장치에 정책을 적용하지 않은 경우 기본 모바일 및 보안에 대한 등록 및 활성화 단계가 있는 알림이 장치에 표시됩니다. 등록을 완료하면 정책이 장치에 적용됩니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>4단계: 지원되지 않는 장치에 대한 전자 메일 액세스 차단

조직 정보를 보호할 수 있도록 기본 이동성 및 보안에서 지원되지 않는 모바일 Microsoft 365 전자 메일에 대한 앱 액세스를 차단해야 합니다. 지원되는 장치 목록은 지원되는 장치를 [참조하세요.](../../admin/basic-mobility-security/capabilities.md)

**앱 액세스를 차단하는 경우:**

1. 브라우저에서 를 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 입력합니다.
2. 조직 **전체 장치 액세스 설정 관리를 선택합니다.**
3. 지원되지 않는 장치를 차단하려면  디바이스가 기본 모바일 및 보안에서 지원되지 않는 경우 에서 차단을 선택하고 Microsoft 365 **를 선택합니다.**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="기본 모바일 및 보안 차단 액세스 옵션입니다.":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>5단계: 조건부 액세스 검사에서 제외할 보안 그룹 선택

모바일 장치에서 조건부 액세스 검사에서 일부 사용자만 제외하고 해당 사용자에 대해 보안 그룹을 하나 이상 만들었다면 여기에 보안 그룹을 추가합니다. 이러한 그룹의 사용자들은 지원되는 모바일 장치에 대해 어떤 정책도 적용되지 않습니다. 조직에서 기본 이동성 및 보안을 더 이상 사용하지 못하게 하려는 경우 이 옵션을 사용하는 것이 좋습니다.

1. 브라우저에서 를 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 입력합니다.

2. 조직 **전체 장치 액세스 설정 관리를 선택합니다.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 모바일 및 보안 정책 옵션을 만들 수 있습니다.":::

3. **추가를** 선택하여 보안 그룹에 대한 액세스가 차단되지 않고 제외하려는 사용자가 있는 보안 그룹을 Microsoft 365. 사용자가 이 목록에 추가된 경우 지원되지 않는 장치를 Microsoft 365 전자 메일에 액세스할 수 있습니다.

4. 그룹 선택 패널에서 사용할 보안 **그룹을** 선택합니다.

5. 이름을 선택한 다음 저장 **추가**  >  **를 선택합니다.**

6. 조직 전체 **장치 액세스** 설정 패널에서 저장 을 **선택합니다.**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="기본 이동성 및 보안 허용 액세스 옵션입니다.":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>보안 정책이 여러 장치 유형에 미치는 영향은 무엇입니까?

사용자 장치에 정책을 적용하는 경우 각 장치에 미치는 영향은 장치 유형에 따라 약간 다릅니다. 다른 장치에 정책이 미치는 영향의 예는 다음 표를 참조합니다.

|**보안 정책**|**Android 4 이상**|**Samsung KNOX**|**iOS 6 이상**|**참고**|
|:-----|:-----|:-----|:-----|:-----|
|암호화된 백업 필요|아니요|예|예|iOS 암호화된 백업이 필요합니다.|
|클라우드 백업 차단|예|예|예|Android에서 Google 백업을 차단(회색으로 표시), iOS에서 클라우드 백업을 차단합니다.|
|문서 동기화 차단|아니요|아니요|예|iOS: 클라우드에서 문서를 차단합니다.|
|사진 동기화 차단 |아니요|아니요|예|iOS(기본): 사진 스트림을 차단합니다.|
|화면 캡처 차단 |아니요|예|예|시도할 때 차단됩니다.|
|비디오 회의 차단 |아니요|아니요|예|IOS에서 FaceTime이 차단되어 Skype 없습니다.|
|진단 데이터 보내기 차단 |아니요|예|예|Android에서 Google 충돌 보고서 보내기 차단|
|앱 스토어에 대한 액세스 차단 |아니요|예|예|Android 홈 페이지에서 앱 스토어 아이콘이 누락되어 Windows, iOS에서 누락됩니다.|
|앱 스토어에 암호 필요 |아니요|아니요|예|iOS: iTunes 구매에 필요한 암호입니다.|
|이동식 저장소에 대한 연결 차단 |아니요|예|해당 없음|Android: SD 카드가 설정에서 회색으로 표시되어 Windows, 설치된 앱을 사용할 수 없습니다.|
|Bluetooth 연결 차단 |참고 사항 보기|참고 사항 보기|예|Android에서는 BlueTooth를 설정으로 사용하지 않도록 설정할 수 없습니다. 대신 BlueTooth가 필요한 모든 트랜잭션(고급 오디오 배포, 오디오/비디오 원격 제어, 핸즈 프리 디바이스, 헤드셋, 전화 액세스 및 직렬 포트)을 사용하지 않도록 설정합니다. 작은 메시지는 이러한 메시지가 사용될 때 페이지 맨 아래에 표시됩니다.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>정책을 삭제하거나 정책에서 사용자를 제거하면 어떻게 하나요?

정책을 삭제하거나 정책이 배포된 그룹에서 사용자를 제거하면 사용자 장치에서 Microsoft 365 프로필 및 캐시된 전자 메일이 제거될 수 있습니다. 다른 장치 유형에 대해 제거된 내용은 다음 표를 참조하세요.

|**제거된 것**|**iOS 6 이상**|**Android 4 이상(Samsung KNOX 포함)**|
|:-----|:-----|:-----|
|관리되는 전자 메일 프로필<sup>1</sup>|예|아니요|
|클라우드 백업 차단|예|아니요|

<sup>1</sup> 전자 메일 프로필 관리  옵션을 사용하여 정책이 배포된 경우 해당 프로필의 관리되는 전자 메일 프로필 및 캐시된 전자 메일이 사용자 장치에서 삭제됩니다.

정책은 각 사용자에 대한 모바일 장치에서 제거됩니다. 기본 이동성 및 보안으로 장치가 다음에 체크 인될 때 정책이 적용됩니다. 이러한 사용자 장치에 적용되는 새 정책을 배포하는 경우 기본 이동성 및 보안에 다시 등록하라는 메시지가 표시될 수 있습니다.

장치를 완전히 지우거나 장치에서 조직 정보를 선택적으로 지울 수도 있습니다. 자세한 내용은 기본 모바일 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)

## <a name="related-content"></a>관련 콘텐츠

[기본 이동성 및 보안](overview.md) 개요(문서)\
[기본 이동성 및 보안](capabilities.md) 기능(문서)