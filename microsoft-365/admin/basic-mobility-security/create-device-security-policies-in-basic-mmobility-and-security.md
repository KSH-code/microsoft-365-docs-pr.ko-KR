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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 모바일 및 보안을 사용 하 여 조직 정보를 보호 하는 장치 정책을 만듭니다.
ms.openlocfilehash: 7bbc4a128505ce6e569db4b4d7d98e132c503965
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337026"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>기본 모바일 및 보안에서 장치 보안 정책 만들기 

기본 이동성 및 보안을 사용 하 여 무단으로 액세스 하지 못하도록 Microsoft 365의 조직 정보를 보호 하는 장치 정책을 만들 수 있습니다. 장치의 사용자에 게 해당 하는 Microsoft 365 라이선스가 있고 기본 Mobility and Security에서 장치를 등록 한 경우 조직의 모든 모바일 장치에 정책을 적용할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

>[!IMPORTANT]
>모바일 장치 정책을 만들려면 기본 이동성 및 보안을 활성화 하 고 설정 해야 합니다. 자세한 내용은 기본 이동성 및 보안 개요를 참조 하세요.

- 기본 Mobility and Security에서 지 원하는 장치, 모바일 장치 앱 및 보안 설정에 대해 알아봅니다. [기본 이동성 및 보안 기능을](capabilities-of-basic-mobility-and-secruity.md)참조 하세요.
- 정책을 배포할 Microsoft 365 사용자를 포함 하는 보안 그룹을 만들고 Microsoft 365에 대 한 차단 된 액세스 권한으로 제외할 수 있는 사용자에 대해 만듭니다. 조직에 새 정책을 배포 하기 전에 소수의 사용자에 게 정책을 배포 하 여 정책 테스트를 수행 하는 것이 좋습니다. 자신을 포함 하는 보안 그룹을 만들고 사용할 수 있으며 Microsoft 365 사용자는 사용자를 대신 하 여 정책을 테스트할 수 있습니다. 보안 그룹에 대 한 자세한 내용은 [보안 그룹 만들기, 편집 또는 삭제](https://go.microsoft.com/fwlink/p/?LinkId=518555)를 참조 하세요.
- Microsoft 365에서 기본 이동성 및 보안 정책을 만들고 배포 하려면 Microsoft 365 글로벌 관리자 여야 합니다. 자세한 내용은 [Security & 준수 센터의 사용 권한을](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)참조 하세요.
- 정책을 배포 하기 전에 조직에서 기본 이동성 및 보안에 따라 장치 등록에 대 한 잠재적인 영향을 알 수 있도록 합니다. 정책을 설정 하는 방법에 따라 비규격 장치는 등록 된 응용 프로그램, 사진 및 개인 정보를 포함 하 여 Microsoft 365 및 데이터에 대 한 액세스를 차단 하 고, 데이터를 삭제할 수 있습니다.

>[!NOTE]
>Microsoft 365 Business Standard for the MDM에서 만든 정책 및 액세스 규칙 exchange 관리 센터에서 작성 된 장치 액세스 규칙 및 모바일 장치 사서함 정책 재정의 장치를 Microsoft 365 Business Standard 용 MDM에 등록 한 후에는 장치에 적용 된 모든 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙이 무시 됩니다. Exchange ActiveSync에 대 한 자세한 정보는 exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)를 참조 하십시오.

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>1 단계: 장치 정책 만들기 및 테스트 그룹에 배포

시작 하기 전에 정품 인증을 수행 하 고 기본 이동성 및 보안을 설정 했는지 확인 합니다. 자세한 내용은 [기본 이동성 및 보안 개요](overview-of-basic-mobility-and-security-for-microsoft-365.md)를 참조 하세요.

1. 브라우저에서를 입력 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.

2. **정책 만들기를**선택 합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 이동성 및 보안 정책 설정":::

3. **정책 설정** 페이지에서 조직의 모바일 장치에 적용 하려는 요구 사항을 지정 합니다.

4. **전자 메일 프로필 관리 필요**: 사용 하도록 설정 된 경우 기본 Mobility and Security로 관리 되는 전자 메일 프로필이 없는 장치는 호환 되지 않는 것으로 간주 됩니다. 장치에 관리 되지 않는 전자 메일 프로필이 제대로 지정 되어 있지 않거나 사용자가 장치에서 전자 메일 계정을 수동으로 설정 하는 경우에는 해당 프로필을 사용할 수 없습니다. 이 설정을 **사용 하지** 않으면 (기본값),이 설정은 규정 준수 또는 비호환을 위해 평가 되지 않습니다. 이 옵션을 선택할 때 사용자가 준수 하는 방법에 대 한 자세한 내용은 [기존 전자 메일 계정을 찾음](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)를 참조 하십시오.

5. **지금이 정책을 적용** 하 시겠습니까? 페이지에서이 정책을 적용 하려는 그룹을 선택 합니다.

6. **이 정책 만들기**를 선택 합니다.

정책은 다음에 모바일 장치를 사용 하 여 Microsoft 365에 로그인 할 때 정책이 적용 되는 각 사용자의 장치에 푸시됩니다. 사용자가 모바일 장치에 정책을 적용 한 적이 없는 경우 정책을 배포한 후에는 기본 이동성 및 보안을 등록 하 고 활성화 하는 단계를 포함 하는 알림을 장치에 받게 됩니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device-using-basic-mobility-and-security.md)을 참조 하세요. Intune 서비스에 의해 호스트 되는 기본 이동성 및 보안에서 등록을 완료 하기 전 까지는 전자 메일, OneDrive 및 기타 서비스에 대 한 액세스가 제한 됩니다. Intune 회사 포털 앱을 사용 하 여 등록을 완료 한 후에는 해당 서비스를 사용할 수 있으며 정책이 장치에 적용 됩니다.

## <a name="step-2-verify-that-your-policy-works"></a>2 단계: 정책이 작동 하는지 확인

장치 정책을 만든 후에는 정책이 조직에 배포 하기 전에 예상 대로 작동 하는지 확인 합니다.

1. 브라우저에서를 입력 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.
2. **관리 장치 목록 보기를**선택 합니다.
3. 정책이 적용 된 사용자 장치의 상태를 확인 합니다. 장치 **상태** 를 **관리 하려고 합니다.**
4. 장치를 선택한 후에는 **관리** 단추에서 **초기화** 를 클릭 하거나 **회사 데이터를 제거** 하 여 장치에서 전체 또는 선택 지우기를 수행할 수도 있습니다. 자세한 내용은 [Microsoft 365에서 모바일 장치 초기화]를 참조 하십시오.

3 단계: 조직에 정책 배포

장치 정책을 만들고 예상 대로 작동 하는지 확인 한 후 조직에 배포 합니다.

1. 브라우저에서 다음을 입력 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.
2. 배포할 정책을 선택 하 고 **적용 대상 그룹** 옆에 있는 **편집** 을 선택 합니다.
3. 추가할 그룹을 검색 하 고 **선택**을 클릭 합니다.
4. **닫기를** 선택 하 고 **설정을 변경 합니다.**
5. 정책 **닫기** 및 **편집을 선택 합니다.**

정책은 다음에 모바일 장치에서 Microsoft 365에 로그인 할 때 정책이 적용 되는 각 사용자의 모바일 장치로 푸시됩니다. 사용자가 모바일 장치에 정책을 적용 하지 않은 경우에는 기본 이동성 및 보안을 위해 등록 하 고 정품 인증을 수행 하는 단계를 포함 하 여 장치에 대 한 알림을 받게 됩니다. 등록을 완료 한 후에는 정책이 해당 디바이스에 적용 됩니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device-using-basic-mobility-and-security.md)을 참조 하세요.

## <a name="step-4-block-email-access-for-unsupported-devices"></a>4 단계: 지원 되지 않는 장치에 대 한 전자 메일 액세스 차단

조직 정보의 보안을 유지 하려면 기본 Mobility and Security에서 지원 하지 않는 모바일 장치에 대 한 Microsoft 365 전자 메일에 대 한 앱 액세스를 차단 해야 합니다. 지원 되는 장치 목록은 [지원 되는 장치](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)를 참조 하세요. 

**앱 액세스를 차단 하려면**

1. 브라우저에서를 입력 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.
2. **조직 차원 장치 액세스 설정을 관리**합니다 .를 선택 합니다.
3. 지원 되지 않는 장치를 차단 하려면 **장치를 Microsoft 365 용 MDM에서 지원 하지 않는 경우**아래에서 **차단을** 선택한 다음 **저장**을 선택 합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="기본 모바일 및 보안 차단 액세스 옵션":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>5 단계: 조건부 액세스 검사에서 제외할 보안 그룹 선택

일부 사용자를 모바일 장치에서 제외 하 고 해당 사용자에 대해 하나 이상의 보안 그룹을 만든 경우 여기에 보안 그룹을 추가 합니다. 이러한 그룹의 사용자는 지원 되는 모바일 장치에 대해 정책이 적용 되지 않습니다. 조직에서 기본 이동성 및 보안을 더 이상 사용 하지 않으려면이 옵션을 선택 하는 것이 좋습니다.

1. 브라우저에서를 입력 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.

2. **조직 차원 장치 액세스 설정을 관리**합니다 .를 선택 합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 모바일 및 보안 정책 만들기 옵션":::

3. **추가** 를 선택 하 여 Microsoft 365에 대 한 차단 된 액세스 권한을 부여 하려는 사용자가 포함 된 보안 그룹을 추가 합니다. 사용자가이 목록에 추가 된 경우 지원 되지 않는 장치를 사용 하는 경우 Microsoft 365 전자 메일에 액세스할 수 있습니다.

4. **그룹 선택** 패널에서 사용 하려는 보안 그룹을 선택 합니다.

5. 이름을 선택 하 고 저장을 **추가**  >  **Save**합니다.

6. 조직 차원 **장치 액세스 설정** 패널에서 **저장**을 선택 합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="기본 이동성 및 보안 허용 액세스 옵션":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>보안 정책이 다른 장치 유형에 미치는 영향은 무엇입니까?

사용자 장치에 정책을 적용 하는 경우 각 장치에 대 한 영향은 장치 유형에 따라 약간씩 다릅니다. 각 장치에 대 한 정책의 영향 예를 확인 하려면 다음 표를 참조 하세요.

|**보안 정책**|**Android 4 이상**|**Samsung KNOX**|**iOS 6 이상**|**참고**|
|:-----|:-----|:-----|:-----|:-----|
|암호화된 백업 필요|아니요|예|예|iOS 암호화 된 백업이 필요 합니다.|
|클라우드 백업 차단|예|예|예|Android에서 Google backup (회색으로 표시), iOS에서 클라우드 백업을 차단 합니다.|
|문서 동기화 차단|아니요|아니요|예|iOS: 클라우드에서 문서를 차단 합니다.|
|사진 동기화 차단 |아니요|아니요|예|iOS (네이티브): 사진 스트림을 차단 합니다.|
|화면 캡처 차단 |아니요|예|예|시도 시 차단 됩니다.|
|화상 회의 차단 |아니요|아니요|예|Facetime이은 Skype 나 다른 사용자가 아닌 iOS에서 차단 됩니다.|
|진단 데이터 보내기 차단 |아니요|예|예|Android에서 Google 충돌 보고서 보내기를 차단 합니다.|
|앱 스토어에 대 한 액세스 차단 |아니요|예|예|Windows에서 사용 하지 않도록 설정 된 Android 홈 페이지의 앱 스토어 아이콘은 iOS에서 누락 되었습니다.|
|앱 스토어에 대 한 암호 필요 |아니요|아니요|예|iOS: iTunes 구매에 암호가 필요 합니다.|
|이동식 저장소에 대 한 연결 차단 |아니요|예|해당 없음|Android: SD 카드를 설정에서 흐리게 표시 됨 Windows가 사용자에 게 알림, 설치 된 앱을 사용할 수 없음|
|Bluetooth 연결 차단 |메모 참조|메모 참조|예|Android에 대 한 설정으로 BlueTooth를 사용 하지 않도록 설정할 수 없습니다. 대신 BlueTooth가 필요한 모든 트랜잭션 (고급 오디오 배포, 오디오/비디오 원격 제어, 핸 즈 프리 장치, 헤드셋, 전화 번호부 액세스 및 직렬 포트)을 사용 하지 않도록 설정 합니다. 이러한 항목 중 하나를 사용 하면 페이지 아래쪽에 작은 toast 메시지가 표시 됩니다.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>정책을 삭제 하거나 정책에서 사용자를 제거 하는 경우 수행 되는 작업

정책을 삭제 하거나 정책을 배포한 그룹에서 사용자를 제거 하면 정책 설정, Microsoft 365 전자 메일 프로필 및 캐시 된 전자 메일이 사용자의 장치에서 제거 될 수 있습니다. 다음 표를 참조 하 여 각 장치 유형에 서 제거 되는 항목을 확인 하십시오.

|**제거 된 기능**|**iOS 6 이상**|**Android 4 이상 (Samsung KNOX 포함)**|
|:-----|:-----|:----------------------|
|관리 되는 전자 메일 프로필<sup>1</sup>|예|아니요|
|클라우드 백업 차단|예|아니요|
<sup>1</sup> **전자 메일 프로필을 관리** 하는 옵션을 사용 하 여 정책이 배포 된 경우 해당 프로필의 관리 되는 전자 메일 프로필과 캐시 된 전자 메일이 사용자 장치에서 삭제 됩니다.

정책은 다음에 장치에서 기본 이동성 및 보안으로 체크 인 될 때 정책이 적용 되는 각 사용자에 대해 모바일 장치에서 제거 됩니다. 이러한 사용자 장치에 적용 되는 새 정책을 배포 하는 경우 기본 이동성 및 보안에 다시 등록 하 라는 메시지가 표시 됩니다.

장치를 완전히 지우거 나 장치에서 조직 정보를 선택적으로 지울 수도 있습니다. 자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요. 

## <a name="related-topics"></a>관련 항목

[기본 이동성 및 보안 개요](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[기본 이동성 및 보안 기능](capabilities-of-basic-mobility-and-secruity.md)
