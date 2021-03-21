---
title: Enterprise State Roaming 사용
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 61b84b3c7b6550a8ce426a3e41630a0d3e269c41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921957"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="6469b-103">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="6469b-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="6469b-104">Microsoft Managed Desktop에서 최상의 환경을 위해 엔터프라이즈 상태 [로밍을](/azure/active-directory/devices/enterprise-state-roaming-overview)사용하도록 설정하면 사용자가 안전하게 사용자 및 응용 프로그램 설정 데이터를 클라우드와 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6469b-104">For the best experience with Microsoft Managed Desktop, enable [Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview), which lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="6469b-105">즉, 로그인하는 Windows 장치에 상관없이 동일한 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6469b-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="6469b-106">예를 들어 Microsoft Managed Desktop 장치 중 하나를 새 장치로 바꾸면 마지막 디바이스와 동일하게 모양과 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6469b-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span>

<span data-ttu-id="6469b-107">Enterprise State Roaming을 사용하도록 설정하려면 [Azure Active Directory에서 엔터프라이즈](/azure/active-directory/devices/enterprise-state-roaming-enable)상태 로밍 사용의 단계를 수행한 다음 이 설명서로 돌아오세요.</span><span class="sxs-lookup"><span data-stu-id="6469b-107">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable), and then return to this documentation.</span></span>

<span data-ttu-id="6469b-108">엔터프라이즈 상태 로밍에 문제가 있는 경우 관리자 지원에 [문의하세요.](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="6469b-108">If you have any difficulty with Enterprise State Roaming, contact Admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="6469b-109">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="6469b-109">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="6469b-110">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="6469b-110">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="6469b-111">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="6469b-111">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="6469b-112">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6469b-112">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="6469b-113">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="6469b-113">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="6469b-114">엔터프라이즈 상태 로밍 사용(이 항목)</span><span class="sxs-lookup"><span data-stu-id="6469b-114">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="6469b-115">장치 설정</span><span class="sxs-lookup"><span data-stu-id="6469b-115">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="6469b-116">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="6469b-116">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="6469b-117">앱 배포</span><span class="sxs-lookup"><span data-stu-id="6469b-117">Deploy apps</span></span>](deploy-apps.md)