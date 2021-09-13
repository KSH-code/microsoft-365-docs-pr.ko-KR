---
title: Office 2013 및 Office 2016 클라이언트 앱에 대해 최신 인증이 작동하는 방법
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: 최신 인증 Microsoft 365 2013 및 2016 클라이언트 앱에 대해 서로 다른 Office 방법을 알아보습니다.
ms.openlocfilehash: 60b1729d9830fd12141d162c4fe721267e52d437
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220795"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Office 2013, Office 2016 및 Office 클라이언트 앱에 대해 최신 인증이 작동하는 방식

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

이 문서를 읽고 Office 2013, Office 2016 및 Office 2019 클라이언트 앱이 Exchange Online, SharePoint Online 및 비즈니스용 Skype Online에 대한 Microsoft 365 테넌트의 인증 구성을 기반으로 최신 인증 기능을 사용하는 방법에 대해 자세히 알아보습니다.

> [!NOTE]
> Office 2010 및 Mac용 Office 2011과 같은 레거시 클라이언트 앱은 최신 인증을 지원하지 않습니다. 기본 인증에만 사용할 수 있습니다.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>서비스용 최신 인증 Microsoft 365 가용성

Microsoft 365 서비스의 경우 최신 인증의 기본 상태는 다음입니다.

- 기본적으로 **Exchange Online** 켜져 있습니다. 최신 [인증을](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) 끄거나 Exchange Online 최신 인증 사용 또는 사용 안 하도록 설정을 참조합니다.

- 기본적으로 **SharePoint** Online에 대해 켜져 있습니다.

- 기본적으로 **비즈니스용 Skype** Online에 대해 켜져 있습니다. 최신 [인증을 비즈니스용 Skype 온라인에서](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)사용하도록 설정을 참조하여 끄거나 으로 설정하세요.

> [!NOTE]
> 2017년 8월 1일 **이전** 에 만든 테넌트의 경우 최신 인증은 Exchange Online 및 비즈니스용 Skype Online에 대해 기본적으로 설정이 **해제** 되어 있습니다.

## <a name="sign-in-behavior-of-office-client-apps"></a>클라이언트 앱의 Office 동작

Office 2013 클라이언트 앱은 기본적으로 레거시 인증을 지원합니다. 레거시란 Microsoft Online 로그인 도우미 또는 기본 인증을 지원하고 있습니다. 이러한 클라이언트가 최신 인증 기능을 사용하려면 Windows 키가 설정되어 있어야 합니다. 자세한 내용은 모바일 장치에서 [Office 2013에](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)대해 최신 인증 Windows 참조하세요.

Microsoft Office 2013이 설치되었고 Windows를 실행 중인 장치(예: 노트북 및 태블릿)에 대해 최신 인증을 사용하려면 다음 레지스트리 키를 설정해야 합니다. 최신 인증을 사용할 각 장치에서 키를 설정해야 합니다.

|**레지스트리 키**|**유형**|**값** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |

[ADAL(최신 인증)을](./hybrid-modern-auth-overview.md) 사용하는 방법을 비즈니스용 Skype 방법을 비즈니스용 Skype.

Office 2016 및 Office 2019 클라이언트는 기본적으로 최신 인증을 지원하며 클라이언트가 이러한 새 흐름을 사용하기 위해 필요한 작업은 없습니다. 그러나 레거시 인증을 사용하려면 명시적 작업이 필요합니다.

아래 링크를 클릭하여 Office 2013, Office 2016 및 Office 2019 클라이언트 인증이 최신 인증이 켜져 있는지 여부에 따라 Microsoft 365 서비스에서 작동하는 방법을 확인하세요.

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [비즈니스용 Skype Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

다음 표에서는 Office 2013, Office 2016 및 Office 2019 클라이언트 앱에 최신 인증을 사용하는지 Exchange Online 클라이언트 앱에 대한 인증 동작에 대해 설명하고 있습니다.

|Office 클라이언트 앱 버전****|레지스트리 키가 있나요?****|최신 인증 설정****|테넌트에 대해 최신 인증이 켜진 인증 동작(기본값)****|테넌트에 대해 최신 인증을 해제한 인증 동작****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |아니요 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |예  <br/> |2013, Outlook 또는 2019에 대해 최신 인증을 강제로 진행합니다. <br/> [추가 정보](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|클라이언트 내에서 최신 인증을 Outlook 합니다.<br/> |
|Office 2019  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL=0  <br/> |아니요  <br/> |기본 인증  <br/> |기본 인증  <br/> |
|Office 2016  <br/> |아니요 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |예  <br/> |2013, 2016 또는 2019에 최신 인증을 강제합니다. <br/> [추가 정보](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|클라이언트 내에서 최신 인증을 Outlook 합니다.<br/> |
|Office 2016  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL=0  <br/> |아니요  <br/> |기본 인증  <br/> |기본 인증  <br/> |
|Office 2013  <br/> |아니요  <br/> |아니요  <br/> |기본 인증  <br/> |기본 인증  <br/> |
|Office 2013  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 기본 인증이 사용됩니다. 테넌트가 사용하도록 설정되지 않은 경우 서버에서 최신 인증을 거부합니다.  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

다음 표에서는 최신 인증을 사용하여 SharePoint Online에 연결할 때 Office 2013, Office 2016 및 Office 2019 클라이언트 앱의 인증 동작에 대해 설명하고 있습니다.

|Office 클라이언트 앱 버전****|레지스트리 키가 있나요?****|최신 인증 설정****|테넌트에 대해 최신 인증이 켜진 인증 동작(기본값)****|테넌트에 대해 최신 인증을 해제한 인증 동작****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증만 해당합니다.  <br/> |연결에 실패했습니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증만 해당합니다.  <br/> |연결에 실패했습니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL = 0  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2016  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증만 해당합니다.  <br/> |연결에 실패했습니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증만 해당합니다.  <br/> |연결에 실패했습니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL = 0  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2013  <br/> |아니요  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2013  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증만 해당합니다.  <br/> |연결에 실패했습니다.  <br/> |

### <a name="skype-for-business-online"></a>비즈니스용 Skype Online
<a name="BK_SFBO"> </a>

다음 표에서는 최신 인증을 사용하여 비즈니스용 Skype Online에 연결할 때 Office 2013, Office 2016 및 Office 2019 클라이언트 앱에 대한 인증 동작에 대해 설명하고 있습니다.

|Office 클라이언트 앱 버전****|레지스트리 키가 있나요?****|최신 인증 설정****|테넌트에 대해 최신 인증이 켜진 인증 동작****|테넌트에 대해 최신 인증이 해제된 인증 동작(기본값)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2019  <br/> |예, EnableADAL = 0  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2016  <br/> |아니요 또는 EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |
|Office 2016  <br/> |예, EnableADAL = 0  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2013  <br/> |아니요  <br/> |아니요  <br/> |Microsoft Online 로그인 도우미만.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |
|Office 2013  <br/> |예, EnableADAL = 1  <br/> |예  <br/> |최신 인증이 먼저 시도됩니다. 서버에서 최신 인증 연결을 거부하면 Microsoft Online 로그인 도우미가 사용됩니다. 온라인 테넌트가 사용하도록 설정되지 비즈니스용 Skype 서버에서 최신 인증을 거부합니다.  <br/> |Microsoft Online 로그인 도우미만.  <br/> |

## <a name="see-also"></a>참고 항목

[Windows 장치에서 Office 2013를 사용하기 위한 최신 인증의 사용](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365에 대한 다단계 인증 사용](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[다단계 Microsoft 365 로그인](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)