---
title: 보안 및 Office 365 센터에서 보안 및 준수 센터로 사용자를 Microsoft 365 규정 준수 센터
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 보안 및 준수 센터 Office 365 자동으로 사용자로 리디렉션하는 방법을 Microsoft 365 규정 준수 센터.
ms.collection: M365-security-compliance
ms.openlocfilehash: 83d6a08d5c189c08c8f7d25daa3af39f28cbf8f1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226278"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>보안 및 Office 365 센터에서 보안 및 준수 센터로 사용자를 Microsoft 365 규정 준수 센터

이 문서에서는 Office 365 보안 및 준수 센터(protection.office.com)에서 Microsoft 365 규정 준수 센터(보안 및 준수 센터)로 규정 준수 솔루션에 액세스하는 사용자에 대해 자동 리디렉션이 작동하는 compliance.microsoft.com.

## <a name="what-to-expect"></a>예상할 일

자동 리디렉션은 Office 365 및 규정 준수(보안 및 준수)에서 다음 준수 관련 솔루션에 액세스하는 모든 사용자에 대해 기본적으로 protection.office.com.

- DLP(데이터 손실 방지)
- 분류
- 정보 거버넌스
- 레코드 관리
- 커뮤니케이션 규정 준수(이전의 '감독')

사용자는 Microsoft 365 규정 준수 센터(compliance.microsoft.com) 규정 준수 솔루션으로 자동으로 라우팅됩니다.

> [!NOTE]
> Office 365 보안 및 준수 센터에 포함된 다른 규정 준수 솔루션의 경우 사용자는 보안 및 준수 센터 또는 Microsoft 365 규정 준수 센터 보안 및 준수 센터에서 Office 365 계속 관리합니다. 이러한 규정 준수 솔루션에 대한 자동 리디렉션은 곧 제공될 예정입니다.*

이 기능과 관련 컨트롤은 Microsoft Defender for Office 365. 보안 기능에 대한 리디렉션을 사용하도록 설정하려면 자세한 내용은 [Microsoft Defender에서](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) Office 365 보안 센터로 Microsoft 365 리디렉션을 참조합니다.

## <a name="can-i-go-back-to-using-the-former-portal"></a>이전 포털을 사용하여 다시 돌아갈 수 있나요?

문제가 사용자에게 작동하지 않는 경우 또는 Microsoft 365 규정 준수 센터 포털을 통해 완료할 수 없는 경우 모든 사용자에 대해 자동 리디렉션을 일시적으로 사용하지 않도록 설정할 수 있습니다.

> [!IMPORTANT]
> 이 Microsoft 365 규정 준수 센터 보안 및 준수 센터에서 현재 관리되는 규정 준수 솔루션의 Office 365 관리 포털입니다. 모든 Microsoft 365 규정 준수 솔루션은 모든 솔루션에서만 Microsoft 365 규정 준수 센터. 사이트로 리디렉션을 Microsoft 365 규정 준수 센터 단기 솔루션이 여야 합니다.*

모든 사용자에 대해 Office 365 보안 및 준수 센터(protection.microsoft.com)로 다시 전환하기 위해 다음 단계를 완료합니다.

1. 전역 관리자로 [](https://compliance.microsoft.com) Microsoft 365 규정 준수 센터 Azure Active Directory에서 규정 준수 관리자 권한이 있는 계정을 사용하여 로그인합니다.
2. 준수 **설정**  >  **리디렉션으로 이동합니다.**
3. 자동 리디렉션 설정을 끄기 로 **전환합니다.**
4. 메시지가 **표시될 때** 끄기 및 피드백 공유를 선택합니다.

사용하지 않도록 설정하면 사용자는 더 이상 compliance.microsoft.com 라우팅되지 Office 365 보안 및 규정 준수 센터(protection.microsoft.com). 전역 또는 규정 준수 관리자가 이 설정을 다시 사용하도록 설정할 수 있습니다.

## <a name="related-information"></a>관련 정보

- [Microsoft 365 규정 준수 센터 개요](/microsoft-365/compliance/microsoft-365-compliance-center)
