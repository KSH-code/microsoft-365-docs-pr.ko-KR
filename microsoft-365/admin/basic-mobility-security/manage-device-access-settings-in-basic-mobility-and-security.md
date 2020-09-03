---
title: 기본 모바일 및 보안에서 장치 액세스 설정 관리
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 이동성 및 보안은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337001"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="0dd1a-103">기본 모바일 및 보안에서 장치 액세스 설정 관리</span><span class="sxs-lookup"><span data-stu-id="0dd1a-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="0dd1a-104">기본 이동성 및 보안을 사용 하는 경우 기본 이동성 및 보안을 사용 하 여 관리할 수 없는 장치가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="0dd1a-105">이러한 경우에는 Exchange ActiveSync 앱에 대해 기본 이동성 및 보안에서 지원 하지 않는 모바일 장치에 대 한 Microsoft 365 전자 메일 액세스를 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="0dd1a-106">이렇게 하면 더 많은 장치에서 조직 정보를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="0dd1a-107">다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-107">Use these steps:</span></span>

1. <span data-ttu-id="0dd1a-108">전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="0dd1a-109">브라우저에서 다음을 입력  [https://protection.office.com](https://protection.office.com/) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="0dd1a-110">Microsoft 365 Business Standard에 대해 MDM을 처음으로 사용 하는 경우 여기에서 [모바일 장치 관리 정품 인증](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="0dd1a-111">정품 인증을 완료 한 후에는 [Office 365 보안 & 준수](https://protection.office.com/)를 사용 하 여 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="0dd1a-112">데이터 손실 방지 > **장치 관리**   >  **장치 정책**으로 이동한 후 **조직 차원 장치 액세스 설정 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="0dd1a-113"> *\*차단을*\*선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="기본 모바일 및 보안 차단 액세스 확인란":::

5. <span data-ttu-id="0dd1a-115"> *\*저장*\*을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-115">Select **Save**.</span></span> 

<span data-ttu-id="0dd1a-116">기본 Mobility and Security에서 지 원하는 장치에 대 한 자세한 내용은 [기본 이동성 및 보안 기능](capabilities-of-basic-mobility-and-secruity.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0dd1a-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>