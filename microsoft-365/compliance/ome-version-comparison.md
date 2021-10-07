---
title: OME(메시지 암호화) 버전 비교
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 이 문서에서는 서로 다른 버전의 두 버전 간의 차이점을 Office 365 메시지 암호화.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 508a129cd472c8843e2af4a012560b17a44c49aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194348"
---
# <a name="compare-versions-of-ome"></a>OME 버전 비교

> [!IMPORTANT]
> 2021년 2월 28일, Microsoft는 2021년 2월 28일부터 AD RMS에 대한 지원을 Exchange Online. Exchange 사서함이 온라인 상태인 하이브리드 환경을 배포한 경우 Active Directory RMS와 함께 IRM을 사용하는 경우 Azure로 마이그레이션해야 합니다. 보통 환경에 배포된 GCC 영향을 받을 수 있습니다. 자세한 내용은 이 문서의 "ad RMS 사용 Exchange Online 개요"를 참조하세요.

이 문서의 나머지에서는 레거시 OME(Office 365 메시지 암호화)와 새로운 OME 기능을 비교하고 Office 365 고급 메시지 암호화. 새로운 기능은 OME 및 IRM(정보 권한 관리)의 병합 및 최신 버전입니다. High에 배포하는 GCC 특성도 간략하게 설명되어 있습니다. 이 두 가지는 조직에서 공존할 수 있습니다. 새 기능의 작동 방식에 대한 자세한 내용은 [OME(Office 365 메시지 암호화)를 참조하세요.](ome.md)

이 문서는 해당 문서에 대한 더 많은 문서 시리즈의 Office 365 메시지 암호화. 이 문서는 관리자 및 ITPros를 위한 것입니다. 암호화된 메시지를 보내거나 받는 데 대한 정보를 찾으면 [OME(Office 365 메시지 암호화)의](ome.md) 문서 목록을 참조하고 요구에 가장 적합한 문서를 찾습니다.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>RMS의 AD RMS 사용 Exchange Online

Exchange Online 전자 메일 메시지 및 첨부 파일에 대한 온라인 및 오프라인 보호를 제공하는 IRM(정보 권한 관리) 기능이 포함되어 있습니다. 기본적으로 Azure Exchange Online 보호를 사용할 수 있습니다. 그러나 조직에서 IRM이 EXCHANGE ONLINE AD RMS(Active Directory Rights Management Service)를 사용하도록 구성한 것일 수 있습니다. AD RMS는 Exchange Online 지원이 중지됩니다. 대신 Azure Information Protection은 AD RMS를 완전히 대체합니다.

이 사용되지 않도록 조직에 영향을 미치는지 평가하려면 에서 [AD RMS를 Azure RMS로](/exchange/troubleshoot/administration/migrate-ad-rms-to-azure)마이그레이션하는 Exchange Online. 이 문서에서는 마이그레이션 옵션에 대한 권장 사항을 제공합니다.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 기능의 나란히 비교

|           **상황**           | **레거시 OME**    | **AD RMS의 IRM**        | **새로운 OME 기능** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*암호화된 메일 보내기*        |메일 Exchange 규칙을 통해|웹용 데스크톱 또는 Outlook 최종 Outlook 시작한 최종 사용자 또는 메일 Exchange 규칙을 통해|Outlook 데스크톱, mac용 Outlook 또는 웹용 Outlook 최종 사용자 메일 Exchange 규칙(전송 규칙) 및 DLP(데이터 손실 방지)를 통해|
|*권한 관리 템플릿*       |   해당 없음      |전달하지 않는 옵션 및 사용자 지정 서식 파일|전달하지 않는 옵션, 암호화 전용 옵션 및 사용자 지정 서식 파일|
|*받는 사람 유형*                   |내부 및 외부 받는 사람|내부 받는 사람만         |내부 및 외부 받는 사람|
|*내부 받는 사람에 대한 환경*|받는 사람은 웹 브라우저 또는 모바일 앱에서 다운로드하여 열 수 있는 HTML 메시지를 받게 됩니다.|클라이언트의 기본 인라인 Outlook 환경|클라이언트를 사용하는 동일한 조직의 받는 사람에 대한 기본 인라인 Outlook 환경입니다.  받는 사람은 OME 포털에서 다른 클라이언트를 사용하여 메시지를 읽을 Outlook 없습니다(다운로드 또는 앱 필요 없음).|
|*외부 받는 사람에 대한 환경*|받는 사람은 웹 브라우저 또는 모바일 앱에서 다운로드하여 열 수 있는 HTML 메시지를 받게 됩니다.|해당 없음|받는 사람에 대한 기본 Microsoft 365 환경입니다. 다른 모든 받는 사람은 OME 포털에서 메시지를 읽을 수 있습니다(다운로드 또는 앱 필요 없음).|
|*첨부 파일 사용 권한*           |첨부 파일에 대한 제한 없음|첨부 파일이 보호됩니다.|첨부 파일은 전달 금지 옵션 및 사용자 지정 서식 파일에 대해 보호됩니다. 관리자는 암호화 전용 옵션의 첨부 파일을 보호할지 여부를 선택할 수 있습니다.|
|*BYOK(Bring Your Own Key) 지원*|없음                |없음               |BYOK 지원          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>레거시 OME에 대한 새로운 OME 기능의 장점

새 기능은 다음과 같은 이점을 제공합니다.

- 암호화 전용 옵션(보안 공동 작업 사용), 전달 금지 옵션 및 사용자 지정 제한을 사용할 수 있습니다.
- 보낸 사람이 Mac 및 클라이언트용 데스크톱, Outlook 데스크톱에서 수동으로 Outlook 수 웹용 Outlook 있습니다.
- Microsoft 365 클라이언트에서 지원되는 인라인 환경을 사용할 Outlook 있습니다. 또는 관리자가 받는 사람에게 브랜드된 환경을 Microsoft 365 수 있습니다.
- Gmail Microsoft 365 Yahoo 및 Microsoft 계정과 같은 사용자 외부의 계정은 OME 포털과 페더러하여 이러한 받는 사람에게 더 나은 사용자 환경을 제공합니다. 다른 모든 ID는 일회성 암호를 사용하여 암호화된 메시지에 액세스합니다.
- 관리자는 브랜드를 사용자 지정하고 여러 브랜징 템플릿을 만들 수 있습니다.
- 관리자는 새로운 기능으로 암호화된 전자 메일을 해지할 수 있습니다.
- 새로운 기능은 보안 및 준수 센터를 통해 자세한 사용 현황 &amp; 보고서를 제공합니다.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 고급 메시지 암호화 기능

Office 365 고급 메시지 암호화 새로운 OME 기능 위에 추가 기능을 제공합니다. 고급 메시지 암호화 Office 365 메시지 암호화 기능을 사용하려면 조직에 새로운 새 보안 기능이 설정되어 있어야 합니다. 또한 이러한 기능을 사용하려면 받는 사람이 OME 포털을 통해 보안 메일을 보고 회신해야 합니다. 고급 기능은 다음과 같습니다.

- 메시지 해지

- 메시지 만료

- 여러 브랜드 템플릿

Office 365 고급 메시지 암호화 높음에서 지원되지 GCC 없습니다.

고급 메시지 암호화 사용에 대한 자세한 내용은 [Office 365 고급 메시지 암호화.](ome-advanced-message-encryption.md)

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>높은 배포에서 Office 365 메시지 암호화 고유한 GCC 특성

높은 환경에서 Office 365 메시지 암호화 사용 GCC 받는 사람 환경과 관련하여 몇 가지 고유한 특성이 있습니다.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>높음과 GCC 받는 사람 GCC 암호화된 전자 메일

보낸 사람이 PC 및 Mac 및 Outlook 및 웹용 Outlook 메일 흐름 규칙을 사용하여 전자 메일을 암호화하는 정책을 Exchange 수 있습니다.

GCC 내 받는 사람은 PC 및 Mac용 Outlook 동일한 인라인 읽기 환경을 웹용 Outlook 수 있습니다.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>높음 및 비영구 GCC 받는 사람 GCC 암호화된 전자 메일

높음 안의 GCC 높은 경계 외부에 암호화된 전자 메일을 보낼 수 GCC 있습니다.

상업용 Microsoft 365 사용자, Outlook.com 사용자 및 Gmail 및 Yahoo와 같은 기타 전자 메일 공급자의 기타 사용자를 포함하여 GCC High 외부의 모든 받는 사람은 래퍼 메일을 받게 됩니다. 이 래퍼 메일은 받는 사람이 메시지를 읽고 회신할 수 있는 OME 포털로 받는 사람을 리디렉션합니다. 이는 OME 암호화 메일을 High로 GCC 외부의 보낸 GCC 마찬가지입니다.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>레거시 OME와 동일한 테넌트의 새로운 기능 동시 사용

동일한 테넌트에서 레거시 OME와 새 기능을 모두 사용할 수 있습니다. 관리자는 메일 흐름 규칙을 만들 때 사용할 OME 버전을 선택하여 이 작업을 할 수 있습니다.

- 레거시 버전의 OME를 지정하기 위해 Exchange 메일 흐름 규칙 작업 **OME의 이전 버전을 적용합니다.**

- 새 기능을 지정하기 위해 메일 흐름 규칙 Exchange 적용 및 권한 Office 365 메시지 암호화 **을 사용 합니다.**

사용자는 데스크톱, Mac용 Outlook 및 Outlook 새로운 기능으로 암호화된 메일을 Outlook 수 웹용 Outlook.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>레거시 OME에서 새 기능으로 마이그레이션

두 버전의 OME를 동시에 사용할 수 있는 경우에도 규칙 작업을 사용하는 이전 메일 흐름 규칙을 편집하여 이전 버전의 **OME를** 적용하여 새 기능을 사용하는 것이 좋습니다. 메일 흐름 규칙 작업 적용 및 권한 보호를 Office 365 메시지 암호화 **이러한 규칙을 업데이트합니다.** 자세한 내용은 [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-ome"></a>OME 시작

일반적으로 새 OME 기능은 조직에서 자동으로 사용하도록 설정됩니다. 조직 내의 새 OME 기능에 대한 자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md)

Azure Information Protection을 사용하도록 설정한 경우 레거시 버전의 OME가 조직에 대해 자동으로 사용하도록 설정됩니다. 과거에는 Azure Information Protection이 활성화되지 않은 경우에도 레거시 OME가 작동했습니다. 이 경우에는 더 이상 해당하지 않습니다.

레거시 OME 사용을 시작하도록 설정한 경우 Azure Information Protection을 사용하도록 설정한 경우 규칙 동작 OME의 이전 버전 적용을 사용하는 메일 흐름 **규칙을 구성합니다.** 자세한 내용은 전자 메일 메시지를 암호화하는 메일 흐름 [규칙 정의를 참조하세요.](define-mail-flow-rules-to-encrypt-email.md)
