---
title: Microsoft Teams
description: 디바이스에 Teams를 설치하고 이후에 업데이트하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950942"
---
# <a name="microsoft-teams"></a><span data-ttu-id="c4bad-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4bad-104">Microsoft Teams</span></span>

<span data-ttu-id="c4bad-105">[Teams는](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 실시간 공동 작업 [및](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) 커뮤니케이션, 모임, 파일 및 앱 공유를 위한 작업 영역도 제공하는 조직을 위한 메시징 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="c4bad-106">초기 배포</span><span class="sxs-lookup"><span data-stu-id="c4bad-106">Initial deployment</span></span>

<span data-ttu-id="c4bad-107">대부분의 하드웨어 공급업체는 아직 Teams를 이미지의 일부로 포함하지 않습니다. 따라서 Microsoft Managed Desktop은 Microsoft Intune을 사용하여 장치에 Teams를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="c4bad-108">모든 관리되는 [장치에는 Teams .msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) 패키지가 설치되어 디바이스에 로그인하는 모든 사용자가 Microsoft Teams를 사용할 준비가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="c4bad-109">패키지가 처음 설치를 마치면 Teams가 자동으로 시작되고 바탕 화면에 바로 가기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="c4bad-110">Microsoft Intune 변경 사항</span><span class="sxs-lookup"><span data-stu-id="c4bad-110">Microsoft Intune changes</span></span>

<span data-ttu-id="c4bad-111">Microsoft Managed Desktop은 Microsoft Teams용 Azure AD 조직에 두 개의 응용 프로그램을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="c4bad-112">디바이스에 따라 64비트 또는 32비트 클라이언트에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="c4bad-113">최신 작업 공간 - Teams 컴퓨터 전체 설치 관리자 x64</span><span class="sxs-lookup"><span data-stu-id="c4bad-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="c4bad-114">최신 작업 공간 - Teams 컴퓨터 전체 설치 관리자 x32</span><span class="sxs-lookup"><span data-stu-id="c4bad-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="c4bad-115">업데이트</span><span class="sxs-lookup"><span data-stu-id="c4bad-115">Updates</span></span>

<span data-ttu-id="c4bad-116">Teams는 엔터프라이즈용 Microsoft 365 앱의 별도 업데이트 경로를 따르고 데스크톱 클라이언트는 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="c4bad-117">Teams는 몇 시간마다 업데이트를 확인하고 다운로드한 다음 컴퓨터가 유휴될 때까지 기다렸다가 업데이트를 자동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="c4bad-118">Teams 제품 그룹은 관리자가 업데이트를 제어할 수 있도록 허용하지 않습니다. 따라서 Microsoft Managed Desktop은 표준 자동 [업데이트 채널을 사용하게 됩니다.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="c4bad-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="c4bad-119">Teams 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="c4bad-119">Manually updating Teams</span></span>

<span data-ttu-id="c4bad-120">개별 사용자는 앱 오른쪽 위에 있는 프로필 드롭다운 메뉴에서 업데이트 확인을 선택하여 업데이트를 다운로드할   수도 \*\*\*\*   있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="c4bad-121">업데이트를 사용할 수 있는 경우 컴퓨터가 유휴일 때 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="c4bad-122">업데이트 배달 최적화</span><span class="sxs-lookup"><span data-stu-id="c4bad-122">Delivery optimization of updates</span></span>

<span data-ttu-id="c4bad-123">Teams 업데이트에 대한 배달 최적화는 기본적으로 켜져 있으며 관리자 또는 사용자의 작업이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4bad-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 