---
title: Office 365, O365 전송, Office 365 스팸 문제, O365 가양성, 검색을 위한 전자 메일 전송, office 365에서 의심 스러운 전자 메일, 메일 검색, 365 피싱에 대 한 Microsoft 검색, Microsoft scan for 피싱, submit for 스팸, 제출 전자 메일, 전송 전자 메일, dodgy 전자 메일, 잘못 된 작업자 메일, 의심 스러운, 신뢰할 수 없는 메일, 보고서 피싱 전자 메일을 microsoft에 보고 하 고 microsoft에 게 microsoft에 사기 전자 메일 신고 받은 편지함의 전자 메일 office 365, 전자 메일 office 365의 바이러스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 테 넌 트에서 의심 스러운 전자 메일, 의심 스러운 메일, 스팸 및 기타 해로운 메시지, Url 및 파일을 검색을 위해 Microsoft에 제출 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033617"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="222e7-103">관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="222e7-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="222e7-104">Exchange Online의 사서함이 있는 Office 365 조직의 관리자 인 경우 Office 365 보안 & 준수 센터의 전송 포털을 사용 하 여 검색을 위해 전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="222e7-105">전자 메일을 제출 하면 메일에 포함 된 Url 및 첨부 파일을 검사 하는 것은 물론 수신 전자 메일을 허용 했을 수 있는 모든 정책에 대 한 정보를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="222e7-106">메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용-보낸 사람 목록 뿐 아니라 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)과 같은 테 넌 트 수준 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="222e7-107">전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 전송 하는 다른 방법에 대해서는 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="222e7-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="222e7-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="222e7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="222e7-109"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="222e7-110">**제출** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/reportsubmission>합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="222e7-111">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="222e7-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="222e7-112">Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="222e7-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="222e7-113">이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="222e7-114">스팸 방지 정책을 추가, 수정 및 삭제 하려면 **조직 관리**, **보안 관리자**또는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="222e7-115">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="222e7-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="222e7-116">사용자가 메시지 및 파일을 Microsoft에 전송 하는 방법에 대 한 자세한 내용은 [Report 메시지 및 파일을 microsoft에](report-junk-email-messages-to-microsoft.md)참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="222e7-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="222e7-117">Office 365 스캐닝을 위해 의심 스러운 콘텐츠를 Microsoft에 게 전달 하는 방법</span><span class="sxs-lookup"><span data-stu-id="222e7-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="222e7-118">Microsoft로 콘텐츠를 전송 하려면 제출 페이지의 왼쪽 위에 있는 **새 제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="222e7-119">전자 메일, URL 또는 파일을 전송 하는 옵션을 사용 하 여 페이지 오른쪽에 플라이 아웃이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="222e7-120">Microsoft에 의심 스러운 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="222e7-120">Submit a questionable email to Microsoft</span></span>

![전자 메일 전송 예](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="222e7-122">전자 메일을 제출 하려면 **전자 메일** 을 선택 하 고 전자 메일 **네트워크 메시지 ID** 를 지정 하거나 전자 메일 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="222e7-123">정책 확인을 실행 하려는 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="222e7-124">정책 확인은 사용자 또는 테 넌 트 수준 정책으로 인해 전자 메일에서 검색이 사용 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="222e7-125">전자 메일이 차단 되었는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="222e7-126">전자 메일이 차단 되어야 하는 경우 스팸, 피싱 또는 맬웨어로 차단 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="222e7-127">어떤 종류의 입력이 가능한 지 모르는 경우 가장 좋은 판단을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="222e7-128">전송 시 정책으로 인해 필터가 생략 되 면 해당 정책에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="222e7-129">하나 이상의 정책으로 인해 필터가 무시 되지 않으면 몇 분 안에 검색이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="222e7-130">상태 링크를 클릭 하 여 전송에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="222e7-131">여기에는 정책 확인 및 다시 검사 결과의 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="222e7-132">참고 Office 365 ATP 전체 필터링 스택을 통해 전자 메일을 다시 실행 하지만 메일, URL 또는 파일의 특정 특성에 따라 부분 다시 검사를 실행 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="222e7-133">**제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="222e7-134">Microsoft에 의심 스러운 URL 보내기</span><span class="sxs-lookup"><span data-stu-id="222e7-134">Send a suspect URL to Microsoft</span></span>

![전자 메일 전송 예](../../media/submission-url-flyout.png)

1. <span data-ttu-id="222e7-136">URL을 제출 하려면 플라이 아웃에서 **url** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="222e7-137">프로토콜 (**https://**)을 포함 하 여 전체 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="222e7-138">**필터**를 선택한 경우 URL이 피싱 또는 맬웨어 인지 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="222e7-139">**제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="222e7-140">Microsoft에 의심 스러운 파일 제출</span><span class="sxs-lookup"><span data-stu-id="222e7-140">Submit a suspected file to Microsoft</span></span>

![전자 메일 전송 예](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="222e7-142">파일을 제출 하려면 플라이 아웃에서 **파일** 을 선택 하 고 검색할 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="222e7-143">**제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="222e7-143">Click the **Submit** button.</span></span>
