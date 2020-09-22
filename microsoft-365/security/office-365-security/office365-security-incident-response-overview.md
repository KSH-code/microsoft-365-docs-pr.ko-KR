---
title: 보안 인시던트 대응
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 이 솔루션은 Microsoft 365에서 가장 일반적인 cybersecurity 공격과 그에 대응 하는 방법에 대해 설명 합니다.
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 221303d43620e89b8200392961d8aa0916c82763
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198706"
---
# <a name="security-incident-response"></a><span data-ttu-id="d106f-103">보안 인시던트 대응</span><span class="sxs-lookup"><span data-stu-id="d106f-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="d106f-104">**요약**: 이 해결 방법은 Office 365에서 가장 일반적인 사이버 보안 공격에 대한 지표와 주어진 공격을 확실하게 확인하는 방법 및 대응하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-104">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="d106f-105">고 사이버 공격에 응답 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-105">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="d106f-106">모든 사이버 공격을 막을 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-106">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="d106f-107">공격자는 계속해서 방어 전략에 대한 새로운 약점을 찾고 있거나 이전 약점을 악용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="d106f-108">공격을 인식하는 방법을 알면 보다 신속하게 대처하여 보안 사고의 기간을 단축시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="d106f-109">이 문서 시리즈는 Microsoft 365에서 특정 유형의 공격을 이해 하 고이를 처리할 수 있는 단계를 제공 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-109">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="d106f-110">다음 사항을 이해하기 위한 빠른 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-110">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="d106f-111">공격이란 무엇인가와 작동 방식</span><span class="sxs-lookup"><span data-stu-id="d106f-111">What the attack is and how it works.</span></span>

- <span data-ttu-id="d106f-112">확인을 위해 IOC(침해 지표)라고 하는 신호 및 해당 신호를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d106f-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="d106f-113">공격을 확실하게 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="d106f-113">How to positively confirm the attack.</span></span>

- <span data-ttu-id="d106f-114">공격을 제거하고 향후에 조직을 더욱 효과적으로 보호기 위해 수행하는 단계</span><span class="sxs-lookup"><span data-stu-id="d106f-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="d106f-115">각 공격 유형에 관한 자세한 정보 링크</span><span class="sxs-lookup"><span data-stu-id="d106f-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="d106f-116">시간이 지남에 따라 더 많은 문서가 추가되기 때문에 매월 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d106f-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="d106f-117">문서 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="d106f-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="d106f-118">Office 365에서 불법 동의 권한 부여 검색 및 교정</span><span class="sxs-lookup"><span data-stu-id="d106f-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="d106f-119">Office 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 재구성</span><span class="sxs-lookup"><span data-stu-id="d106f-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="d106f-120">인시던트 대응 문서</span><span class="sxs-lookup"><span data-stu-id="d106f-120">Incident response articles</span></span>

- [<span data-ttu-id="d106f-121">Office 365에서 손상된 이메일 계정에 응답</span><span class="sxs-lookup"><span data-stu-id="d106f-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="d106f-122">사이버 보안 프로그램과 같은 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="d106f-122">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="d106f-123">Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-123">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="d106f-124">Microsoft 365 조 직을 보호 하기 위한 Microsoft 권장 모범 사례를 구현 하려면 [microsoft 365 보안 로드맵-처음 30 일, 90 일 및 그 이상에 해당 하는 주요 우선 순위](security-roadmap.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-124">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="d106f-125">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="d106f-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="d106f-126">이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-126">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="d106f-127">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="d106f-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="d106f-128">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="d106f-129">90일 초과</span><span class="sxs-lookup"><span data-stu-id="d106f-129">Beyond 90 days.</span></span> <span data-ttu-id="d106f-130">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="d106f-130">These enhancements build in your first 90 days work.</span></span>
