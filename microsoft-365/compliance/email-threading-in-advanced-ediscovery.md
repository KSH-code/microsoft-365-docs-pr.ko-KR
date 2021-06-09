---
title: 전자 메일 스레딩 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 전자 메일 Advanced eDiscovery 수행하면 전자 메일 스레딩이 전자 메일 대화를 구문 분석하고 각 메시지를 서로 다른 범주로 구분합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285564"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="8ac7f-103">전자 메일 스레딩 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8ac7f-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="8ac7f-104">한 동안 진행된 전자 메일 대화를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="8ac7f-105">대부분의 경우 스레드의 마지막 전자 메일에는 이전의 모든 전자 메일의 내용이 포함됩니다. 마지막 전자 메일을 검토하면 스레드에서 발생된 대화의 전체 컨텍스트가 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="8ac7f-106">전자 메일 스레딩은 검토자가 컨텍스트를 잃지 않고 수집된 문서의 일부를 검토할 수 있도록 이러한 전자 메일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="8ac7f-107">전자 메일 스레딩은 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="8ac7f-107">What does email threading do?</span></span>

<span data-ttu-id="8ac7f-108">전자 메일 스레딩은 각 전자 메일을 구문 분석하고 개별 메시지로 해지합니다. 각 전자 메일은 개별 메시지의 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="8ac7f-109">그런 다음 검토 집합의 모든 전자 메일을 분석하여 전자 메일에 고유한 콘텐츠가 있는지 또는 체인이 다른 전자 메일에 전체적으로 포함되어 있는지 여부를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="8ac7f-110">최종 전자 메일은 다음과 같은 네 가지 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="8ac7f-111">**포괄**: 전자 메일의 마지막 메시지에 고유한 콘텐츠가 있으며 전자 메일에는 다른 전자 메일에 포함된 모든 첨부 파일이 있으며 이 전자 메일에 콘텐츠가 전체적으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="8ac7f-112">**일부 제외 포괄**: 전자 메일의 마지막 메시지에 고유한 콘텐츠가 있지만 해당 콘텐츠가 이 전자 메일에 전부 포함되어 있는 다른 전자 메일에 포함된 일부 첨부 파일은 전자 메일에 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="8ac7f-113">**사본 포괄**: 포괄/일부 제외 포괄 전자 메일의 정확한 복사본</span><span class="sxs-lookup"><span data-stu-id="8ac7f-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="8ac7f-114">**미포괄**: 이 전자 메일의 콘텐츠는 하나 이상의 포괄/일부 제외 포괄로 표시된 전자 메일에 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="8ac7f-115">이 대화와 다른 Outlook?</span><span class="sxs-lookup"><span data-stu-id="8ac7f-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="8ac7f-116">이 소리는 한 눈에 보기에서 대화 그룹화와 Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="8ac7f-117">그러나 몇 가지 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-117">However, there are some important distinctions.</span></span> <span data-ttu-id="8ac7f-118">두 개의 대화로 포크된 전자 메일 대화를 고려합니다. 예를 들어, 대화의 마지막 두 전자 메일에 고유한 콘텐츠가 있도록 누군가가 대화의 최신 전자 메일이 아닌 전자 메일에 응답했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="8ac7f-119">Outlook 전자 메일을 단일 대화로 그룹화합니다. 마지막 전자 메일만 읽으면 고유한 콘텐츠가 포함된 두 번째 전자 메일의 컨텍스트가 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="8ac7f-120">전자 메일 스레딩은 각 전자 메일을 개별 구성 요소로 구문 분석하고 비교하기 때문에 전자 메일 스레딩은 마지막 두 전자 메일을 모두 포함으로 표시하여 포괄으로 표시된 모든 전자 메일을 읽는 한 컨텍스트를 누락하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac7f-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
