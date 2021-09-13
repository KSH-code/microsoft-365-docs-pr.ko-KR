---
title: 인증되지 않은 공유에 대한 모범 사례
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 이 문서에서는 인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례를 알아봅니다.
ms.openlocfilehash: 19791a532b6ea9a7167ac85dfe1eb1b58b9f8f1b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59217902"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a>인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례

인증되지 않은 공유(*모든 사용자* 링크)는 다양한 상황에서 편리하며 유용합니다. *모든 사용자* 링크는 가장 간편하게 공유하는 방법입니다. 사용자가 인증 없이 링크를 열 수 있으며 다른 사용자에게 무료로 전달할 수 있습니다.

일반적으로 조직의 일부 콘텐츠가 인증되지 않은 공유에 적합한 것은 아닙니다. 이 문서에서는 사용자가 파일 및 폴더의 인증되지 않은 공유를 할 수 있지만, 조직의 콘텐츠를 보호하는 데 도움이 되는 보호 기능도 포함된 환경을 만들 수 있는 옵션을 다룹니다.

> [!NOTE]
> 인증되지 않은 공유가 작동하려면 조직 및 사용자가 사용할 개별 사이트 또는 팀에 대해 이 기능을 사용하도록 설정해야 합니다. 활성화하려는 시나리오를 보려면 [조직 외부 사용자와 공동 작업](collaborate-with-people-outside-your-organization.md)을 참조하세요.

## <a name="set-an-expiration-date-for-anyone-links"></a>모든 사용자 링크의 만료 날짜를 설정합니다.

파일은 오랜 기간 동안 사이트, 그룹 및 팀에 저장되는 경우가 많습니다. 경우에 따라, 파일을 수년 동안 보존해야 하는 데이터 보존 정책이 있을 수 있습니다. 해당 파일을 인증되지 않은 사용자와 공유하는 경우, 나중에 파일에 대한 예기치 않은 액세스 및 변경 내용이 발생할 수 있습니다. 이와 같은 가능성을 줄이기 위해 *모든 사용자* 링크의 만료 시간을 구성할 수 있습니다.

*모든 사용자* 링크가 만료되면 계정을 더 이상 콘텐츠에 액세스하는 데 사용할 수 없습니다.

조직 전반에서 모든 사용자 링크의 만료 날짜를 설정하려면 다음 작업을 수행합니다.

1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. 왼쪽 탐색에서 **정책** 을 확장한 후 **공유** 를 클릭합니다.
3. **"모든 사용자" 링크 만료 및 사용 권한 옵션 선택** 에서 **이러한 링크는 다음 기간 내에 만료되어야 합니다** 확인란을 선택합니다.</br>
   ![SharePoint 조직 수준 모든 사용자 링크 만료 설정 스크린샷.](../media/sharepoint-organization-anyone-link-expiration.png)
4. 상자에 일 수를 입력한 다음 **저장** 을 클릭합니다.

특정 사이트에서 모든 사용자 링크의 만료 날짜를 설정하려면 다음 작업을 수행합니다.

1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. 왼쪽 탐색에서 **사이트** 를 확장한 후 **활성 사이트** 를 클릭합니다.
3. 변경할 사이트를 선택한 다음 **공유** 를 클릭합니다.
4. **모든 사용자 링크에 대한 고급 설정** 에서 **모든 사용자 링크 만료** 에서 **조직 수준 설정과 동일** 확인란의 선택을 취소합니다.</br>
   ![SharePoint 사이트 수준 모든 사용자 링크 만료 설정 스크린샷.](../media/sharepoint-organization-anyone-link-expiration-site.png)
5. **이러한 링크는 이 기간 내에 만료되어야 함** 옵션을 선택하고 상자에 일 수를 입력합니다.
6. **저장** 을 클릭합니다.

*모든 사용자* 링크가 만료되면 파일이나 폴더를 새 *모든 사용자* 링크와 다시 공유할 수 있습니다.

[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite)를 사용하여 특정 OneDrive에 대한 *모든 사용자* 링크 만료를 설정할 수 있습니다.

## <a name="set-link-permissions"></a>링크 사용 권한 설정

파일의 *모든 사용자* 링크를 사용하여 파일을 편집할 수 있으며, 폴더의 *모든 사용자* 링크를 통해 파일을 확인하고 편집하며 새 파일을 해당 폴더에 업로드할 수 있습니다. 파일 및 폴더에 대한 사용 권한을 보기 전용으로 변경할 수 있습니다.

인증되지 않은 공유를 허용하지만, 인증되지 않은 사용자가 조직의 콘텐츠를 수정하는 것이 우려되는 경우, 파일 및 폴더 사용 권한을 **보기** 로 설정하는 것이 좋습니다.

조직 전반에서 모든 사용자 링크의 사용 권한을 설정하려면 다음 작업을 수행합니다.

1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. 왼쪽 탐색 창에서 **공유** 를 클릭합니다.
3. **"모든 사용자" 링크의 고급 설정** 에서 사용할 파일 및 폴더 사용 권한을 선택합니다.</br>
   ![SharePoint 조직 수준 모든 사용자 링크 사용 권한 설정 스크린샷.](../media/sharepoint-organization-anyone-link-permissions.png)

*모든 사용자* 링크가 **보기** 로 설정된 경우, 게스트와 파일 및 폴더를 계속 공유하고 *특정 사용자* 링크를 사용하여 편집 권한을 부여할 수 있습니다. 이러한 링크를 사용하려면 조직 외부의 사용자가 게스트로 인증해야 하며, 이 링크와 공유되는 파일 및 폴더에서 게스트 활동을 추적하고 감사할 수 있습니다.

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a>기본 링크 유형이 조직에 있는 사용자에 대해서만 작동하도록 설정합니다.

*모든 사용자* 공유가 사용자 조직에 사용할 수 있도록 설정된 경우, 기본 공유 링크는 일반적으로 **모든 사용자** 로 설정됩니다. 이 기능이 사용자에게는 편리하지만, 원하지 않는 인증되지 않는 공유의 위험이 높아질 수 있습니다. 사용자가 중요한 문서를 공유하는 동안 링크 유형을 변경하는 것을 잊어버린 경우, 사용자가 인증이 필요 없는 공유 링크를 실수로 만들 수 있습니다.

기본 링크 설정을 조직 내부 사용자만 사용할 수 있는 링크로 변경하여 이 위험을 완화할 수 있습니다. 인증되지 않은 사용자와 공유하려는 사용자는 해당 옵션을 구체적으로 선택해야 합니다.

조직에 대한 기본 파일 및 폴더 공유 링크를 설정하려면 다음 작업을 수행합니다.
1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. 왼쪽 탐색 창에서 **공유** 를 클릭합니다.
3. **파일 및 폴더 링크** 에서 **조직 내 사용자만** 을 선택합니다.

   ![SharePoint 기본 링크 유형 설정 스크린샷](../media/sharepoint-default-sharing-link-company-link.png)

4. **저장** 을 클릭합니다.

특정 사이트에 대한 기본 파일 및 폴더 공유 링크를 설정하려면 다음 작업을 수행합니다.
1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. 왼쪽 탐색에서 **사이트** 를 확장한 후 **활성 사이트** 를 클릭합니다.
3. 변경할 사이트를 선택한 다음 **공유** 를 클릭합니다.
4. **기본 공유** 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소합니다.

   ![SharePoint 사이트 수준의 기본 링크 유형 설정 스크린샷.](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. **조직의 사용자만** 옵션을 선택하고 **저장** 을 클릭합니다.

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a>중요한 콘텐츠의 인증되지 않은 공유 방지

[DLP(데이터 손실 방지)](../compliance/dlp-learn-about-dlp.md)를 사용하여 중요한 콘텐츠의 인증되지 않은 게스트와의 공유를 방지할 수 있습니다. 데이터 손실 방지는 파일 자체의 파일 민감도 레이블, 보존 레이블 또는 중요한 정보를 기반으로 하는 조치를 취할 수 있습니다.

DLP 규칙을 만들려면 다음을 수행합니다.
1. Microsoft 365 준수 관리 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention)로 이동합니다.
2. **정책 만들기** 를 클릭합니다.
3. **사용자 지정** 을 선택하고 **다음** 을 클릭합니다.
4. 정책 이름을 입력한 후 **다음** 을 클릭합니다.
5. **정책을 적용할 위치** 페이지에서 **SharePoint 사이트** 및 **OneDrive 계정** 을 제외한 모든 설정을 해제한 후 **다음** 을 클릭합니다.
6. **정책 설정 정의** 페이지에서 **다음** 을 클릭합니다.
7. **고급 DLP 규칙 사용자 지정** 페이지에서 **규칙 만들기** 를 클릭하고 규칙의 이름을 입력합니다.
8. **조건** 에서 **조건 추가** 를 클릭하고 **콘텐츠 포함** 을 선택합니다.
9. **추가** 를 클릭하고 인증 되지 않은 공유를 방지하려는 정보 유형을 선택합니다.

   ![조건 옵션, 중요한 정보 유형, 민감도 레이블, 보존 레이블 스크린샷.](../media/limit-accidental-exposure-dlp-conditions.png)

10. **작업** 에서 **작업 추가** 를 클릭하고 **액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 를 선택합니다.
11. **Microsoft 365 위치의 콘텐츠에 대한 액세스 제한 또는 암호화** 확인란을 선택한 다음 **“링크에 대한 모든 사용자" 옵션을 통해 콘텐츠에 대한 액세스 권한을 부여받은 유일한 사용자** 를 선택합니다.

      ![DLP 규칙 작업 옵션의 스크린샷.](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. **저장** 을 클릭한 다음 **다음** 을 클릭합니다.
13. 테스트 옵션을 선택하고 **다음** 을 클릭합니다.
14. **제출** 을 클릭한 다음 **완료** 를 클릭합니다.

## <a name="protect-against-malicious-files"></a>악성 파일로부터 보호

익명 사용자가 파일을 업로드할 수 있도록 허용하는 경우 악성 파일이 업로드되는 위험이 증가하게 됩니다. Microsoft 365에서는 Office 365용 Defender에서 *안전한 첨부 파일* 기능을 사용하여 업로드된 파일을 자동으로 검사하고 안전하지 않은 파일을 격리할 수 있습니다.

안전한 첨부 파일을 설정하려면
1. 보안 및 준수 관리 센터에서 [ATP 안전한 첨부 파일 페이지](https://protection.office.com/safeattachmentv2)를 엽니다.
2. **전역 설정** 을 클릭합니다.
3. SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기

   ![보안 및 규정 준수 센터의 안전한 첨부 파일 설정 스크린샷](../media/safe-attachments-setting.png)

4. 필요에 따라 안전한 문서를 켠 다음 **저장** 을 클릭합니다.

추가 지침은 [SharePoint, OneDrive 및 Microsoft Teams용 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md)의 경우 [SharePoint, OneDrive 및 Microsoft Teams용 ATP 설정](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md)을 참조하시기 바랍니다.

## <a name="add-copyright-information-to-your-files"></a>파일에 저작권 정보 추가

Microsoft 365 규정 준수 관리 센터에서 민감도 레이블을 사용하는 경우, 조직의 Office 문서에 워터마크나 머리글 또는 바닥글을 자동으로 추가하도록 레이블을 구성할 수 있습니다. 따라서 공유된 파일에 저작권 또는 기타 소유권 정보가 포함되도록 할 수 있습니다.

레이블이 지정된 파일에 바닥글을 추가하려면

1. [Microsoft 365 규정 준수 관리 센터](https://compliance.microsoft.com)를 엽니다.
2. 왼쪽 탐색 창에서 **솔루션** 의 **정보 보호** 를 클릭합니다.
3. 바닥글을 추가하려는 레이블을 클릭한 다음 **레이블 편집** 을 클릭합니다.
4. **다음** 을 클릭하여 **콘텐츠 표시** 탭으로 이동한 다음, 콘텐츠 표시를 **설정** 합니다. 
5. 추가하려는 텍스트 유형의 확인란을 선택한 다음, **텍스트 사용자 지정** 을 클릭합니다.
6. 문서에 추가하려는 텍스트를 입력하고 원하는 텍스트 옵션을 선택한 다음, **저장** 을 클릭합니다.</br>
   ![민감도 레이블의 콘텐츠 표시 설정 스크린샷](../media/content-marking-for-anonymous-sharing.png).
7. **다음** 을 클릭하여 마법사의 끝에 도달하고 **레이블 저장** 을 클릭합니다.

레이블에 콘텐츠 표시를 사용하는 경우, 사용자가 해당 레이블을 적용하면 사용자가 지정한 텍스트가 Office 문서에 추가됩니다.

## <a name="see-also"></a>참고 항목

[민감도 레이블 개요](/Office365/SecurityCompliance/sensitivity-labels)

[게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한](share-limit-accidental-exposure.md)

[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)
