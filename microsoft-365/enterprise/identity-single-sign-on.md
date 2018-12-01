---
title: '10단계: 사용자 로그인 간소화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Seamless SSO(Seamless Single Sign-On)를 이해하고 구성합니다.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870262"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="f780f-103">10단계: 사용자 로그인 간소화</span><span class="sxs-lookup"><span data-stu-id="f780f-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="f780f-104">*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="f780f-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f780f-p101">이 단계에서는 사용자가 암호 및 사용자 이름(대부분의 경우)을 입력하지 않고도 Azure AD 사용자 계정을 사용하는 서비스에 로그인할 수 있도록 Azure AD Seamless SSO(Azure Active Directory Seamless Single Sign-On)를 설정합니다. 이는 사용자가 ID 페더레이션 서버와 같은 추가 온-프레미스 구성 요소 없이도 Office 365와 같은 클라우드 기반 응용 프로그램에 보다 쉽게 액세스할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="f780f-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="f780f-107">Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f780f-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="f780f-108">[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f780f-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f780f-110">테스트 랩 가이드: Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="f780f-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="f780f-111">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f780f-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f780f-112">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f780f-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="f780f-113">Office 365 로그인 페이지 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f780f-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

