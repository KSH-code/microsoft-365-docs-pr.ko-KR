<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>필수: 조직의 보안 및 정보 보호 수준 정의

조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.

최소한 다음 세 가지 보안 수준을 사용합니다.

- 기준
- 중요
- 높은 규제

필요한 경우 [1단계](../infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step4"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>필수: Microsoft 365에 대한 향상된 보안 구성

[Office 365 보안 강화](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 위해 다음과 같은 설정을 구성했습니다.

- Microsoft 365 보안 및 준수 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint 관리 센터의 테넌트 수준 공유 정책
- Azure AD(Azure Active Directory)의 설정

또한 [SharePoint, OneDrive 및 Microsoft Teams용 Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://docs.microsoft.com/ko-KR/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)했습니다.

필요한 경우 [3단계](../infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step3"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>선택: 전체 사용자 환경에서 분류 구성

법률 및 규정 준수 팀과 협력하여 조직의 데이터 거버넌스 및 보안 정책에 적합한 분류 및 레이블 지정 체계를 개발하기 위해 작업하였습니다. 

해당 정책은 다음과 같은 구성 및 배포에 해당합니다.

- 중요한 데이터 유형
- 보존 레이블
- 민감도 레이블
- Azure Information Protection 레이블

필요한 경우 [2단계](../infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365의 권한이 부여된 액세스 관리 구성

[Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목의 정보를 사용하여 권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들었습니다. 이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 Just in-Time 액세스가 활성화됩니다.

필요한 경우 [4단계](../infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다. 
