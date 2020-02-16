---
title: 암호화된 전자 메일 보내기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook을 사용 하 여 암호화 된 전자 메일을 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 559998326caedaf3352741ad9083940f79b1a614
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080463"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="b305f-103">중요 한 전자 메일 암호화 또는 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="b305f-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="b305f-104">데이터 및 캠페인 정보가 중요 하 고 기밀을 유지 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="b305f-105">사용자와 전자 메일 받는 사람이 해당 정보를 필요한 민감도로 취급할 수 있도록 암호화 및 민감도 레이블을 사용 하 여 이러한 중요 한 정보를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="b305f-106">모범 사례</span><span class="sxs-lookup"><span data-stu-id="b305f-106">Best practices</span></span>

<span data-ttu-id="b305f-107">기밀 또는 중요 한 정보가 포함 된 전자 메일을 보내기 전에 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="b305f-108">**암호화:** 전자 메일을 암호화 하 여 전자 메일의 정보에 대 한 개인 정보를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="b305f-109">전자 메일 메시지를 암호화 하면 읽을 수 있는 일반 텍스트에서 스크램블 된 cypher 텍스트로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="b305f-110">메시지를 암호화 하는 데 사용 되는 공개 키와 일치 하는 개인 키가 있는 받는 사람만 메시지를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="b305f-111">그러나 해당 하는 개인 키가 없는 받는 사람은 해독이 되지 않은 텍스트를 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="b305f-112">관리자는 특정 조건을 충족 하는 메시지를 자동으로 암호화 하는 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="b305f-113">예를 들어 관리자는 조직 외부에서 전송 된 모든 메시지를 암호화 하는 규칙 또는 특정 단어나 구를 언급 하는 모든 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="b305f-114">모든 암호화 규칙이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="b305f-115">**민감도 레이블:** 또한 캠페인은 사용자가 캠페인의 정보 보호 정책을 준수 하도록 파일 및 전자 메일에 적용할 수 있는 민감도 레이블을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="b305f-116">레이블을 설정 하면 전자 메일 (예: 메시지에 머리글 표시)을 사용 하 여 우편물 레이블을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![레이블 및 암호화에 대 한 설명선이 포함 된 전자 메일 다이어그램](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="b305f-118">설정하기</span><span class="sxs-lookup"><span data-stu-id="b305f-118">Set it up</span></span>

<span data-ttu-id="b305f-119">미리 정의 된 규칙을 충족 하지 않는 메시지를 암호화 하거나 관리자가 규칙을 설정 하지 않은 경우 메시지를 보내기 전에 다양 한 암호화 규칙을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="b305f-120">Outlook 2013 또는 2016 또는 Mac 용 Outlook 2016에서 암호화 된 메시지를 보내려면 **> 사용 권한 옵션**을 선택 하 고 필요한 보호 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="b305f-121">웹용 Outlook에서 **보호** 단추를 선택 하 여 암호화 된 메시지를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="b305f-122">자세한 내용은 [Outlook FOR PC에서 암호화 된 메시지 보내기, 보기 및 회신을](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b305f-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="b305f-123">관리 설정</span><span class="sxs-lookup"><span data-stu-id="b305f-123">Admin settings</span></span>

<span data-ttu-id="b305f-124">전자 메일 암호화 설정에 대 한 자세한 내용은 [Office 365의 전자 메일 암호화](https://docs.microsoft.com/office365/securitycompliance/email-encryption)를 통해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="b305f-125">자동으로 전자 메일 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="b305f-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="b305f-126">관리자는 캠페인에서 보내고 받는 전자 메일 메시지를 자동으로 보호 하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="b305f-127">규칙을 설정 하 여 보내는 전자 메일 메시지를 암호화 하 고 조직 내부에서 들어오는 암호화 된 메시지에서 암호화를 제거 하 고 조직에서 보낸 암호화 된 메시지에 대 한 회신을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="b305f-128">메일 흐름 규칙을 만들어 새 Office 365 메시지 암호화 (OME) 기능을 사용 하 여 전자 메일 메시지를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="b305f-129">EAC (Exchange 관리 센터)를 사용 하 여 새 OME 기능으로 메시지 암호화를 트리거하는 메일 흐름 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="b305f-130">웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="b305f-131">관리 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="b305f-132">관리 센터에서 **관리 센터 > Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="b305f-133">자세한 내용은 [Office 365에서 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 정의](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b305f-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="b305f-134">암호화 메시지 브랜드</span><span class="sxs-lookup"><span data-stu-id="b305f-134">Brand your encryption messages</span></span>

<span data-ttu-id="b305f-135">캠페인 브랜딩을 적용 하 여 전자 메일 메시지의 모양과 텍스트를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b305f-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="b305f-136">자세한 내용은 [암호화 된 메시지에 조직의 브랜드 추가](https://docs.microsoft.com/office365/securitycompliance/email-encryption)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b305f-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

