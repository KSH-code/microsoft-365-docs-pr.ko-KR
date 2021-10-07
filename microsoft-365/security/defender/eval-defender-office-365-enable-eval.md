---
title: 프로덕션 환경에서 Microsoft Defender용 평가 Office 365 사용하도록 설정
description: 평가판을 위해 Microsoft Defender를 활성화하는 Office 365, 평가판 라이선스, MX 레코드 처리, & 및 인바운드 연결 감사를 수행합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 72ee60efdfa93444d6f1fbde7d1c15dd203fdae8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176694"
---
# <a name="enable-the-evaluation-environment"></a>평가 환경 사용

**적용 대상:**
- Microsoft 365 Defender

이 문서는 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [3단계](eval-defender-office-365-overview.md) 중 2단계입니다Office 365. 이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-office-365-overview.md)

다음 단계에 따라 Microsoft Defender for Office 365.

![Microsoft Defender 평가 환경에서 Microsoft Defender를 Office 365 설정하는 단계입니다.](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [1단계: 평가판 라이선스 활성화](#step-1-activate-trial-licenses)
- [2단계: 공용 MX 레코드 감사 및 확인](#step-2-audit-and-verify-the-public-mx-record)
- [3단계: 허용 도메인 감사](#step-3-audit-accepted-domains)
- [4단계: 인바운드 커넥터 감사](#step-4-audit-inbound-connectors)
- [5단계: 평가 활성화](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>1단계: 평가판 라이선스 활성화

사용자 환경 또는 테넌트 관리 포털에 Office 365 Microsoft Defender에 로그온합니다.

1. 관리 포털로 이동합니다.
2. 빠른 실행에서 서비스 구매를 선택합니다.

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="검색 창의 탐색 창에서 서비스 구매를 Office 365.":::

3. 아래로 스크롤하여 Add-On(또는 "Defender"를 검색)하여 계획에 대한 Microsoft Defender를 Office 365 찾습니다.
4. 평가할 계획 다음에 있는 세부 정보를 클릭합니다.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="세부 정보 단추를 클릭하고 다음을 클릭합니다.":::

5. 무료 *평가판 시작 링크를* 클릭합니다.

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="이 패널에서 무료 평가판 시작 *하이퍼링크*를 클릭합니다.":::

6. 요청을 확인하고 지금 시도 *단추를* 클릭합니다.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="이제 지금 시도 *단추*를 클릭합니다.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>2단계: 공용 MX 레코드 감사 및 확인

Microsoft Defender를 효과적으로 Office 365 위해 인바운드 외부 전자 메일은 테넌트와 연결된 EOP(Exchange Online Protection) 인스턴스를 통해 릴레이하는 것이 중요합니다.

1. M365 관리 포털에 로그온하고 설정 도메인을 선택합니다.
2. 확인된 전자 메일 도메인을 선택하고 DNS 관리를 클릭합니다.
3. 생성된 MX 레코드를 기록해 두어 EOP 테넌트에 할당합니다.
4. 외부(공용) DNS 영역으로 액세스하고 전자 메일 도메인과 연결된 기본 MX 레코드를 검사합니다.
    - *공용 MX* 레코드가 현재 할당된 EOP 주소(예: tenant-com.mail.protection.outlook.com)와 일치하는 경우 더 이상 라우팅 변경이 필요하지 않습니다.
    - 공용 MX 레코드가 현재 타사 또는 사내 SMTP 게이트웨이로 확인되면 추가 라우팅 구성이 필요한 것일 수 있습니다.
    - 공용 MX 레코드가 현재 Exchange 경우 일부 받는 사람 사서함이 아직 EXO로 마이그레이션되지 않은 하이브리드 모델에 있을 수 있습니다.

## <a name="step-3-audit-accepted-domains"></a>3단계: 허용 도메인 감사

1. Exchange Online 관리 포털에 로그온하고 메일 Flow 선택한 다음 허용 도메인을 클릭합니다.
2. 테넌트에서 추가 및 확인된 허용 도메인 목록에서 기본 전자  메일 도메인의 도메인 유형을 메모합니다.
    - 도메인 유형이 ***Authoritative로*** 설정된 경우 조직의 모든 받는 사람 사서함이 현재 해당 도메인에 Exchange Online.
    - 도메인 유형이 내부  릴레이로 설정된 경우 여전히 일부 받는 사람 사서함이 여전히 사내에 있는 하이브리드 모델에 있을 수 있습니다.

## <a name="step-4-audit-inbound-connectors"></a>4단계: 인바운드 커넥터 감사

1. Exchange Online 관리 포털에 로그온하고 메일 Flow 선택한 다음 커넥터를 클릭합니다.
2. 구성된 커넥터 목록에서 파트너 조직에 있으며 타사 SMTP 게이트웨이와 상관 관계가 있을 수 있는 항목을 기록합니다. 
3. 구성된 커넥터 목록에서 조직의 전자 메일 서버에서 아직  하이브리드 시나리오에 있는 것으로 표시될 수 있는 항목을 메모합니다.

## <a name="step-5-activate-the-evaluation"></a>5단계: 평가 활성화

여기에 있는 지침을 사용하여 microsoft Defender에서 Office 365 평가를 위해 Microsoft 365 Defender 활성화합니다.

1. Microsoft 365 Defender 포털에 액세스할 수 있는 계정으로 테넌트에 로그온합니다.
2. 검색 포털을 Microsoft 365 Defender  관리용 Microsoft Defender의 기본 인터페이스로 만들지 여부를 Office 365(권장).

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="설정 켜기 단추를 클릭하여 중앙 집중식 및 향상된 관리 Microsoft 365 Defender 포털을 사용합니다.":::

3. 탐색 메뉴에서 전자 메일 & **공동 작업에서** 정책 & *선택합니다.*

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="다음은 정책 및 & 있는 전자 메일 & 그림입니다. 클릭하세요!":::

4. 정책 정책 *& 대시보드에서* 위협 **정책을 클릭합니다.**

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="정책 정책 & 규칙 대시보드와 위협 정책을 가리킹하는 화살표의 그림입니다. 다음을 클릭합니다!":::

5. 아래로 스크롤하여 *추가 정책으로* 이동한 후 타일에 대한 **Defender Office 365** 선택합니다.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Eval Defender for Office 365 전자 메일 및 공동 작업 벡터에서 30일 평가판으로 & 있습니다. 클릭할 수 있습니다.":::

6. 이제 외부 전자 메일 경로를 직접 Exchange Online 또는 타사 게이트웨이 또는 서비스로 라우팅할지 선택하고 다음을 클릭합니다.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 사서함으로의 메일 Exchange Online 평가합니다. 메일을 라우팅하는 아웃바운드 커넥터의 이름을 포함하여 메일이 지금 라우팅된 방식에 대한 세부 정보를 제공합니다. EOP(Exchange Online Protection)만 사용하는 경우 커넥터가 없습니다. Choose one of I'm using a 3rd-party or on-premises provider, or I only use EOP.":::

7. 타사 게이트웨이를 사용하는 경우 드롭다운 목록에서 해당 솔루션과 연결된 인바운드 커넥터와 함께 공급업체 이름을 선택합니다. 답변을 나열한 후 다음을 클릭합니다.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="이 대화 상자에서 조직에서 사용하고 있는 제3자 공급업체 서비스를 선택하거나 *Other*를 선택합니다. 다음 대화 상자에서 인바운드 커넥터를 선택합니다. 그런 다음 다음을 클릭합니다.":::

8. 설정을 검토하고 평가 만들기 **단추를** 클릭합니다.

   |Before|이후|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="이 창에는 설정을 검토할 수 있는 드롭다운이 있습니다. 필요한 경우 라우팅 유형 편집에 대한 클릭 가능한 링크도 있습니다. 준비가 되면 큰 파란색 평가판 만들기 단추를 클릭합니다.":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="이제 설정이 완료되었습니다. 이 페이지의 파란색 단추에 '평가판으로 이동'으로 표시됩니다.":::|
   |

## <a name="next-steps"></a>다음 단계

3단계 중 3단계: Microsoft Defender용 파일럿 Office 365

Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365

평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)
