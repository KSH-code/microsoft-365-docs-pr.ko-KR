---
title: 외부 전자 메일 전달, 자동 전달, 5.7.520 액세스 거부, 외부 전달을 사용 하지 않도록 설정, 관리자가 외부 전달을 사용 하지 않도록 설정, 아웃 바운드 스팸 방지 정책
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f729aa816caf8fb07499037ee27fbfc37b7205b3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202882"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Office 365에서 외부 전자 메일 전달 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


외부 전달은 *아웃 바운드 스팸 방지 정책* 에 의해 제어 되며 구성 된 설정에 따라 사용자에 게 범위가 지정 됩니다. 현재 3 개의 설정이 지원 됩니다.

- **자동** -이 모드에서는 전달 된 메시지가 허용 되는지 여부를 결정 하는 시스템을 담당 합니다.  기본 모드 이며이 모드에서는 시스템이 자동 외부 전달을 차단 합니다.

- **설정** – 자동 외부 전달은 허용 되며 제한 되지 않습니다.

- **Off** -자동 외부 전달은 사용 하지 않도록 설정 되며 최종 사용자에 게 NDR (배달 못 함 보고서)이 생성 됩니다.

이러한 설정을 구성 하는 방법에 대 한 자세한 내용은 [EOP에서 아웃 바운드 스팸 필터링 구성을](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) 참조 하세요.

> [!NOTE]
> 자동 전달을 사용 하지 않도록 설정 하면 메시지를 외부 주소로 리디렉션하는 받은 편지함 규칙도 사용할 수 있습니다.

## <a name="controlling-external-email-forwarding"></a>외부 전자 메일 전달 제어

조직의 관리자는 받은 편지함 규칙 또는 SMTP 전달을 사용 하 여 전자 메일을 자동으로 전달할 수 있는 사용자를 제한 하거나 제어 하기 위한 회사 요구 사항이 있을 수 있습니다. 전자 메일 전달은 유용한 기능 일 수 있지만 조직이 나 파트너를 공격 하는 데 활용할 수 있는 공격자에 게 정보를 제공 하는 경우에도 정보 노출을 초래할 수 있습니다.

Office 365에서는 받은 편지함 규칙 또는 메일 상자 구성에서 자동 외부 전달을 허용 하지 않으므로 보안 기본 정책을 제공 합니다. 그러나 관리자는 조직의 모든 사용자 또는 일부에 대해 이러한 설정을 수정할 수 있습니다. 내부 사용자 간에 메시지를 전달 하는 것은 이러한 수정의 영향을 받지 않습니다.

> [!NOTE]
> Office 365에서 외부 주소로 자동 전달을 사용 하지 않도록 설정 하는 작업은 [메시지가 센터](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 게시물을 통해 전달 되는 세부 정보와 함께 단계별로 진행 되 고 있습니다. 관리자가 이러한 변경 내용을 준비할 수 있도록 하기 위해 사용자에 게 중단이 발생 하지 않도록 사전에 정책을 수정 하 게 됩니다.

조직에서 자동 전달 (받은 편지함 규칙 또는 SMTP 전달)을 사용 하는 사용자에 대 한 자세한 내용은 [자동 전달 메시지 보고서](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true)에서 찾을 수 있습니다.

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>이 정책이 다른 자동 전달 컨트롤에서 작동 하는 방식

관리자는 [원격 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 의 자동 전달을 차단 하 고 Etr (Exchange 전송 규칙) 사용과 같은 다른 유형의 컨트롤을 이미 배치할 수 있습니다. 원격 도메인에 대해 자동 전달을 허용 하지만 아웃 바운드 스팸 정책을 통한 자동 전달을 차단 하는 경우에는 이러한 두 컨트롤이이 특정 기능에 독립적입니다. 마찬가지로, 아웃 바운드 스팸 정책에서 자동 전달을 허용 하지만 ETR 또는 원격 도메인에서 메시지를 차단 하는 경우에는 이러한 컨트롤 중 하나에 의해 메시지가 차단 됩니다. 예를 들어 아웃 바운드 스팸 정책에서 자동 전달을 허용 하 고 원격 도메인을 이용 하 여 사용자가 메시지를 자동으로 전달할 수 있는 도메인을 제어할 수 있습니다.


## <a name="the-blocked-email-forwarding-message"></a>차단 된 전자 메일 전달 메시지

메시지가 자동으로 전달 되는 것으로 감지 되 고 조직 정책에서 해당 활동을 *차단* 하는 **배달 못 함 보고서 (NDR)** 가 최종 사용자에 게 다시 생성 됩니다. 보고서에서 메시지가 배달 되지 않았음을 나타냅니다. NDR의 형식은 다음과 같습니다. 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
