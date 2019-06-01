---
title: Microsoft 365 Business에 대 한 위협 요소 보호 강화
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection을 설정 하 고 중요 한 데이터를 보호 합니다.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668399"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="5cdb5-103">규정 준수 기능 설정</span><span class="sxs-lookup"><span data-stu-id="5cdb5-103">Set up compliance features</span></span>

<span data-ttu-id="5cdb5-104">Microsoft 365 Business에는 데이터 및 장치를 보호 하기 위한 기능이 제공 되며, 사용자와 고객의 중요 한 정보를 안전 하 게 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="5cdb5-105">DLP 기능 설정</span><span class="sxs-lookup"><span data-stu-id="5cdb5-105">Set up DLP features</span></span>

<span data-ttu-id="5cdb5-106">PII(개인 식별 정보)를 보호하도록 정책을 설정하는 방법의 예제를 보려면 [템플릿에서 DLP 정책 만들기](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="5cdb5-p101">DLP는 사용 준비가 완료된 여러 다른 로캘용 정책 템플릿을 제공합니다. 예를 들어, 오스트레일리아 재무 데이터, 캐나다 개인 정보 보호법, 미국 재무 데이터 등이 있습니다. 전체 목록을 보려면 [DLP 정책 템플릿에 포함되는 내용](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)을 참조하세요. 이러한 모든 템플릿은 PII 템플릿 예제와 비슷한 방식으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-p101">DLP comes with many ready-to-use policy templates for many different locales. For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list. All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="5cdb5-110">Exchange Online Archiving을 사용하여 전자 메일 보존 설정</span><span class="sxs-lookup"><span data-stu-id="5cdb5-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="5cdb5-111">**Exchange Online 보관** 라이선스 기능은 eDiscovery에 대 한 전자 메일 콘텐츠를 보존 하 여 준수 및 규제 표준을 유지 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="5cdb5-112">또한 서 소송이의 이벤트로 인 한 위험을 줄이고, 보안 위반 후 또는 삭제 된 항목을 복구 해야 하는 경우 데이터를 복구할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="5cdb5-113">소송 보존을 사용 하 여 모든 사용자의 콘텐츠를 보존 하거나 보존 정책을 사용 하 여 보존 하려는 항목을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="5cdb5-114">**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="5cdb5-115">사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="5cdb5-116">왼쪽 탐색 영역에서 **사용자** \> **활성 사용자**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="5cdb5-117">해당 사서함에 소송 보존을 적용하려는 사용자를 선택하고 사용자 창에서 **메일 설정**을 확장하고 **기타 설정** 옆에 있는 **Exchange 속성 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="5cdb5-118">사용자의 사서함 페이지에서 왼쪽 탐색 영역의 \*\* 사서함 기능\*\*을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="5cdb5-p103">**소송 보존** 대화 상자의 **소송 보존 기간** 필드에서 소송 보존 기간을 지정할 수 있습니다. 무한 보존을 적용하려면 이 필드를 비워 둡니다. 메모를 추가하여 사서함 소유자에게 소송 보존 \>에 대해 추가로 설명해야 하는 웹 사이트를 알려주고 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-p103">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold. You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="5cdb5-p104">**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-p104">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="5cdb5-123">Azure Information Protection 기능 설정</span><span class="sxs-lookup"><span data-stu-id="5cdb5-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="5cdb5-124">AIP (Azure Information Protection)를 사용 하면 레이블을 적용 하 여 문서와 전자 메일을 분류 하 고 선택적으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="5cdb5-125">규칙 및 조건을 정의 하는 관리자가 사용자에 의해 수동으로 또는 사용자에 게 권장 사항을 제공 하는 조합을 사용 하 여 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="5cdb5-126">웹용 Outlook에서 전자 메일에 다음과 같은 기본 제공 레이블 및 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="5cdb5-127">**전달 금지**: 받는 사람은 메시지를 읽을 수 있지만 콘텐츠를 전달, 인쇄 또는 복사할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="5cdb5-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="5cdb5-128">**Encrypt**: 전체 메시지가 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="5cdb5-129">받는 사람은 암호화 된 콘텐츠에 액세스 하기 전에 해당 id를 확인 해야 하며 암호화를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="5cdb5-p107">**기밀**: 조직의 직원들에게 전자 메일 콘텐츠 및 첨부 파일에 대한 모든 권한을 부여하지만, 조직 외부의 사람에게는 이러한 권한을 부여하지 않습니다. 데이터 소유자는 언제든지 콘텐츠를 추적하고 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-p107">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization. Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="5cdb5-p108">**극비**: 이 제한은 극비 데이터에 적용할 수 있으며, 직원들이 데이터를 보고, 편집하고, 회신할 수 있지만 전달, 인쇄 또는 복사할 수는 없도록 합니다. 데이터 소유자는 언제든지 콘텐츠를 추적하고 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-p108">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data. Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="5cdb5-134">Azure Information Protection이 활성화되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="5cdb5-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="5cdb5-135">AIP가 활성화되었는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="5cdb5-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="5cdb5-136">[Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="5cdb5-137">**모든 서비스**를 선택하고 **검색 상자**에 *Azure Information Protection*을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="5cdb5-138">결과가 표시되면 **Azure Information Protection** 옆에 있는 시작을 클릭하여 즐겨찾기로 지정하고 나중에 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="5cdb5-139">**Azure Information Protection** \> **보호 활성화**를 선택하고 상태가 활성화됨으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="5cdb5-140">Azure Information Protection 정책 및 기본 레이블 보기</span><span class="sxs-lookup"><span data-stu-id="5cdb5-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="5cdb5-141">기존 레이블을 보고 수정하려면</span><span class="sxs-lookup"><span data-stu-id="5cdb5-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="5cdb5-142">Azure Information Protection 대시보드에서 **분류** \> **레이블**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="5cdb5-143">![Azure Information Protection의 표준 레이블](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="5cdb5-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="5cdb5-144">옵션을 보려면 아무 레이블이나 선택합니다. 표시 이름, 색 등을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="5cdb5-145">고유한 레이블을 만들려면 [레이블 수정 및 새로 만들기](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="5cdb5-146">수동으로 Azure Information Protection 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="5cdb5-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="5cdb5-147">AIP 클라이언트를 수동으로 설치하려면</span><span class="sxs-lookup"><span data-stu-id="5cdb5-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="5cdb5-148">[Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53018)에서 **AzInfoProtection.exe**를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="5cdb5-149">Word 문서를 보고 **홈** 탭에서 **보호** 옵션을 사용할 수 있는지 확인하여 설치가 제대로 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="5cdb5-150">![Word 문서의 보호 탭 드롭다운](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="5cdb5-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="5cdb5-151">자세한 내용은 [클라이언트 설치](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cdb5-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
