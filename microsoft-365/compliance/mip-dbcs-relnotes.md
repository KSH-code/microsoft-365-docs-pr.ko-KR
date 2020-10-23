---
title: 이중 바이트 문자 집합 릴리스 노트(미리 보기)를 위한 Microsoft 365 규정 준수 지원
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 더블 바이트 문자 집합에 대한 지원을 위한 릴리스 노트
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681504"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="93354-103">더블 바이트 문자 집합 릴리스 노트(미리보기)를 지원</span><span class="sxs-lookup"><span data-stu-id="93354-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="93354-104">Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="93354-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="93354-105">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="93354-105">Chinese (simplified)</span></span>
- <span data-ttu-id="93354-106">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="93354-106">Chinese (traditional)</span></span>
- <span data-ttu-id="93354-107">한국어</span><span class="sxs-lookup"><span data-stu-id="93354-107">Korean</span></span>
- <span data-ttu-id="93354-108">일본어</span><span class="sxs-lookup"><span data-stu-id="93354-108">Japanese</span></span>

<span data-ttu-id="93354-109">이 지원은 중요한 정보 유형 및 키워드 사전에서 사용할 수 있으며 데이터 손실 방지, 통신 규정 준수, Exchange 온라인, SharePoint 온라인, OneDrive for Business 및 Teams 솔루션에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="93354-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="93354-110">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="93354-110">Known issues</span></span>

- <span data-ttu-id="93354-111">전자 메일에 첨부된 텍스트 파일이 BOM(바이트 순서 표시)이 없는 UTF-8 형식인 경우, 통신 준수 정책에서 전자 메일이 탐지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93354-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="93354-112">정책 조건에 대해 "메시지에는 다음 단어가 포함되어 있습니다"라는 문장을 입력하면 통신 규정 준수 정책이 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93354-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="93354-113">정책에 지정된 텍스트가 단어로 작성되면 검색이 가능하지만, 문장 중간에 작성되면 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93354-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="93354-114">사전을 유형 정보로 지정하는 통신 준수 정책은 팀 개인 대화 및 채널 대화를 탐지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93354-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="93354-115">이 단계에서는 통신 규정 준수에 대해 다음 조건이 지원되지 않습니다(향후 이러한 문제를 해결할 계획임).</span><span class="sxs-lookup"><span data-stu-id="93354-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="93354-116">"메세지에 다음 단어가 포함되어 있습니다."</span><span class="sxs-lookup"><span data-stu-id="93354-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="93354-117">"메세지에 다음 단어가 없습니다."</span><span class="sxs-lookup"><span data-stu-id="93354-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="93354-118">"첨부에는 이러한 단어가 포함되어 있습니다."</span><span class="sxs-lookup"><span data-stu-id="93354-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="93354-119">"첨부에는 이러한 단어가 포함되어 있습니다."</span><span class="sxs-lookup"><span data-stu-id="93354-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="93354-120">대신 메시지 및 첨부 파일 간의 패턴을 탐지할 키워드 사전이 있는 사용자 정의 SIT(중요한 정보 유형)을 만들고 이 사용자 정의 SIT를 통신 규정 준수 정책 조건으로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93354-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
