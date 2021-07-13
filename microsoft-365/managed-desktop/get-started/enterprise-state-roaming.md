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
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409119"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="574ab-103">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="574ab-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="574ab-104">[Enterprise 상태 로밍을](/azure/active-directory/devices/enterprise-state-roaming-overview) 사용하면 사용자 및 응용 프로그램 설정 데이터를 클라우드와 안전하게 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="574ab-105">즉, 로그인하는 디바이스에 상관없이 동일한 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="574ab-106">예를 들어 해당 Microsoft Managed Desktop 장치 중 하나를 새 장치로 바꾸면 마지막 장치와 정확히 동일하게 보이고 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="574ab-107">Enterprise 상태 로밍은 사용자에 대해 구성할 수 있는 Microsoft Managed Desktop 서비스에 대한 선택적 기능으로, Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="574ab-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="574ab-108">상태 Enterprise 사용하도록 설정하려면 에서 Enterprise 상태 로밍 사용의 단계를 [Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)</span><span class="sxs-lookup"><span data-stu-id="574ab-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="574ab-109">상태 로밍을 Enterprise 설정하면 장치 설정 중에 선택한 언어를 기본 설정 언어 목록에서 덮어 덮어 들이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="574ab-110">사용자가 이 문제를 쉽게 해결할 수 있는 경우 초기에는 지역화 환경이 불일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="574ab-111">장치를 Enterprise 상태 로밍이 사용자에게 적합한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="574ab-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="574ab-112">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="574ab-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="574ab-113">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="574ab-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="574ab-114">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="574ab-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="574ab-115">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="574ab-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="574ab-116">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="574ab-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="574ab-117">상태 Enterprise 사용(이 항목)</span><span class="sxs-lookup"><span data-stu-id="574ab-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="574ab-118">장치 설정</span><span class="sxs-lookup"><span data-stu-id="574ab-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="574ab-119">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="574ab-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="574ab-120">앱 배포</span><span class="sxs-lookup"><span data-stu-id="574ab-120">Deploy apps</span></span>](deploy-apps.md)
