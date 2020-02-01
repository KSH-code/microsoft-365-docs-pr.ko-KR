---
title: 모바일 장치 관리 인프라 종료 조건
description: Microsoft 365 Enterprise는 Microsoft Intune을 사용 하는 모바일 장치 관리를 포함 합니다. 요구 사항 및 필수 구성 요소를 검토 하 고, Azure Active Directory 리소스를 사용 하 여 Intune을 설정 하 고, iOS, macOS, Android 및 Windows 장치를 등록 하 고, 앱을 배포 하 고, 프로필 구성, 준수 정책을 사용 하 고, 모바일에 조건부 액세스 사용 Microsoft 365 Enterprise를 사용한 장치 관리
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, 모바일 장치 관리, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600885"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="71257-105">모바일 장치 관리 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="71257-105">Mobile device management infrastructure exit criteria</span></span>

![5단계: 모바일 디바이스 관리](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="71257-107">*이는 Microsoft 365 Enterprise E3 및 E5 버전에 적용 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="71257-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="71257-108">구성이 모바일 장치 관리 인프라에 대 한 다음 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="71257-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="71257-109">Intune은 Azure Active Directory (Azure AD) 사용자 및 그룹 만들기를 포함 하 여 조직의 장치에 대 한 규칙을 적용할 수 있도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71257-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="71257-110">사용자가 만든 정책을 장치가 수락할 수 있도록 Intune에서 장치를 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="71257-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="71257-111">사용자가 Exchange Online 및 SharePoint Online과 같은 조직의 Microsoft 365 클라우드 서비스에 액세스할 수 있도록 장치에 앱이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="71257-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="71257-112">사용자가 만든 Azure AD 사용자 및 그룹을 사용하여 바이러스 백신 사용 및 특정 앱 제한과 같은 기능이 구성되고 사용자 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71257-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="71257-113">장치에서 방화벽 또는 암호 길이를 요구 하는 준수 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71257-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="71257-114">장치가 호환 되지 않으면 조건부 액세스에서 조직의 데이터에 대 한 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="71257-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="71257-115">결과 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="71257-115">Results and next steps</span></span>

<span data-ttu-id="71257-116">장치가 Intune에 등록 되 고 적절 한 정책으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71257-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![6단계: 정보 보호](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="71257-118">Microsoft 365 Enterprise의 종단 간 배포를 위한 단계를 수행 하는 경우 다음 단계는 [정보 보호](infoprotect-infrastructure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="71257-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
