---
title: 보낸 사람 도메인 정보 문제 해결
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 보낸 사람 도메인에 대 한 정보를 수정 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635175"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="857f1-103">보낸 사람 도메인 정보 문제 해결</span><span class="sxs-lookup"><span data-stu-id="857f1-103">Fix sender domain insight</span></span>

<span data-ttu-id="857f1-104">Microsoft 365에서는 특정 보안 기준을 충족 하기 위해 내부 온-프레미스 전자 메일 환경에서 Microsoft 365로 메시지를 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="857f1-105">Microsoft 365에서 인바운드 커넥터를 만들어 원본 IP 주소 또는 인증서를 사용 하 여 온-프레미스 전자 메일 서버에서 SMTP 연결을 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="857f1-106">Microsoft 365을 통해 외부 세계를 통해 전자 메일을 릴레이 하도록 온-프레미스 전자 메일 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="857f1-107">구성에서 다음 문 중 하나에 해당 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="857f1-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="857f1-108">보낸 사람의 전자 메일 도메인이 조직에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="857f1-109">자세한 내용은 Office 365에서 도메인 추가를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="857f1-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="857f1-110">온-프레미스 전자 메일 서버는 인증서를 사용 하 여 microsoft 365에 전자 메일을 보내거나, 인증서가 Microsoft 365에 등록 한 도메인 이름과 정확히 일치 하거나, 해당 도메인을 사용 하 여 Microsoft 365에 인증서 기반 커넥터를 만들었다고 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="857f1-111">조건을 충족 하지 않는 메시지는 조직에 대 한 특성을 사용 하지 않으며 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="857f1-112">**Fix sender domain** 통찰력은 온-프레미스 환경에서 조건을 충족 하지 않는 전자 메일을 표시 하 고, 온-프레미스 전자 메일 환경에서 잠재적으로 손상 된 컴퓨터와 사용자 계정을 식별 하 고, 수정 작업을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드에서 보낸 사람 도메인 통찰력 수정](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="857f1-114">**자세히 보기**를 클릭 하면 다음 다이어그램에 나와 있는 것과 같이 다른 widget이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![보낸 사람 도메인 문제 해결의 세부 정보 위젯](../../media/sender-domain-view-details.png)

<span data-ttu-id="857f1-116">메시지를 Office 365로 배달 하는 데 사용 된 인바운드 커넥터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="857f1-117">**예제 메시지 id 보기** 를 클릭 하 여 온-프레미스 전자 메일 환경에서 전송 된 메시지에 대 한 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="857f1-118">이러한 메시지는 Office 365에서 거부 되었기 때문에 메시지 추적을 사용할 수는 없지만, 샘플 메시지 id를 사용 하 여 온-프레미스 전자 메일 환경에서 메시지를 추적할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857f1-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![보낸 사람 도메인 정보 수정에서 예제 메시지 id 보기](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="857f1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="857f1-120">See also</span></span>

<span data-ttu-id="857f1-121">메일 흐름 대시보드의 다른 메일 흐름 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="857f1-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
