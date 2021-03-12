---
title: 메시지 암호화 뷰어 앱 사용 안
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: OME(Office 365 메시지 암호화) 뷰어 앱은 2018년 Android 및 Apple 스토어에서 제거되었습니다.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741525"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="e0082-103">메시지 암호화 뷰어 앱 사용 안</span><span class="sxs-lookup"><span data-stu-id="e0082-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="e0082-104">2018년 8월 15일, Android 및 Apple 스토어에서 OME(Office 365 메시지 암호화) 뷰어 모바일 앱을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="e0082-105">Office 365 메시지 암호화 뷰어 모바일 앱은 Apple 및 Android 휴대폰에서 이전 버전의 OME로 암호화된 전자 메일 메시지 및 첨부 파일을 읽는 데 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="e0082-106">OME 뷰어 앱을 제거하는 것 외에도 이전 버전의 OME는 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="e0082-107">2018년 8월 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e0082-107">Changes from August 2018</span></span>

<span data-ttu-id="e0082-108">2017년 9월에 발표된 것 처럼, 사용자가 모바일 앱의 요구 사항 없이도 암호화되고 보호된 메시지를 조직 내부 또는 외부의 사용자에게 보낼 수 있도록 새로운 [버전의 Office 365](https://aka.ms/ome2017) 메시지 암호화를 출시했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="e0082-109">그 이후로 추가 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="e0082-110">암호화 전용 템플릿</span><span class="sxs-lookup"><span data-stu-id="e0082-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="e0082-111">첨부 파일 암호 해독 제어</span><span class="sxs-lookup"><span data-stu-id="e0082-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

<span data-ttu-id="e0082-112">이 변경으로 사용자는 8월 1일부터 더 이상 Office 365 메시지 암호화 뷰어 모바일 앱을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="e0082-113">따라서 메일 받는 사람은 일부 Android 및 Apple 모바일 장치에서 이전 버전의 OME로 암호화된 메시지를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="e0082-114">그러나 데스크톱 브라우저를 통해 개인 컴퓨터에서 이러한 메시지를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="e0082-115">이미 앱을 다운로드한 사용자는 계속 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="e0082-116">이러한 변경이 이행된 이유</span><span class="sxs-lookup"><span data-stu-id="e0082-116">Why this change was made</span></span>

<span data-ttu-id="e0082-117">새 버전의 OME는 더 이상 모바일 앱이 보호된 전자 메일 메시지 및 첨부 파일을 읽을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="e0082-118">새로운 OME 기능을 사용하는 고객은 Outlook 모바일에서 보호된 메시지를 볼 수 있으며 비 고객은 브라우저에서 보호된 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="e0082-119">사용자가 모바일 앱을 다운로드하도록 요구하는 것은 고객이 보호된 메시지를 볼 수 있는 또 다른 Hurdle입니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="e0082-120">새로운 Office 365 메시지 암호화 기능은 더 나은 모바일 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="e0082-121">이전 버전의 Office 365 메시지 암호화를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="e0082-122">Office 365 메시지 암호화의 이전 버전은 현재 더 이상 사용되지 않을 예정입니다. 그러나 새로운 버전의 Office 365 메시지 암호화가 크게 향상되어 사용자가 Outlook(데스크톱, 모바일)에서 보호된 메시지를 직접 읽을 수 있는 기능을 포함하여 모든 사용자와 디바이스에서 중요한 데이터를 더 쉽게 암호화하고 보호할 수 있습니다. 및 web)</span><span class="sxs-lookup"><span data-stu-id="e0082-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="e0082-123">이 변경을 준비하기 위해 해야 할 일</span><span class="sxs-lookup"><span data-stu-id="e0082-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="e0082-124">조직에서 현재 OME 뷰어 앱이 필요한 받는 사람에게 암호화된 첨부 파일을 전송하는 경우 설명서 및 교육 리소스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="e0082-125">조직에서 새 기능과 향상된 기능을 활용할 수 있도록 현재 버전의 OME를 사용하기 위해 기존 Exchange 메일 흐름 규칙을 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="e0082-126">새 OME 기능을 설정한 후 받는 사람은 OME 뷰어 앱이 모바일 장치에서 암호화된 메시지를 읽을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="e0082-127">조직에 적절한 새 OME 기능으로 이동하는 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0082-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="e0082-128">자세한 내용은 [Set up new Office 365 Message Encryption capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="e0082-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="e0082-129">새 기능의 작동 방식에 대한 자세한 내용은 [Office 365 메시지 암호화를 참조하세요.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="e0082-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

