# 테라폼 설치하기

_기준 버전: 1.10.5_

> ## 맥OS
> 
> ### 패키지 관리자
> 
> ``` shell
> brew tap hashicorp/tap
> brew install hashicorp/tap/terraform
> ```
> 
> ### 바이너리 파일 다운로드
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_darwin_amd64.zip)
>
> [ARM64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_darwin_arm64.zip)

> ## 윈도우
>
> ### 바이너리 파일 다운로드
> [386](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_windows_386.zip)
>
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_windows_amd64.zip)

> ## 리눅스
>
> ### 패키지 관리자
>
> #### 우분투/데비안
>
> ``` shell
> wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
> echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
> sudo apt update && sudo apt install terraform
> ```
>
> #### 센트OS/RHEL
> ``` shell
> sudo yum install -y yum-utils
> sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
> sudo yum -y install terraform
> ```
> 
> #### 페도라
> ``` shell
> sudo dnf install -y dnf-plugins-core
> sudo dnf config-manager addrepo --from-repofile=https://rpm.releases.hashicorp.com/fedora/hashicorp.repo
> sudo dnf -y install terraform
> ```
>
> #### 아마존 리눅스
> ``` shell
> sudo yum install -y yum-utils shadow-utils
> sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
> sudo yum -y install terraform
> ```
>
> #### 홈브루
> ``` shell
> brew tap hashicorp/tap
> brew install hashicorp/tap/terraform
> ```
>
> ### 바이너리 파일 다운로드
>
> [386](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_linux_386.zip)
>
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_linux_amd64.zip)
>
> [ARM](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_linux_arm.zip)
>
> [ARM64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_linux_arm64.zip)
>
> ### 참고
>
> <!-- TODO Link the document below after translating it -->
> 이 [튜토리얼](https://developer.hashicorp.com/well-architected-framework/operational-excellence/verify-hashicorp-binary)을 완료하여 모든 리눅스 배포판에서 HashiCorp 도구를 설치하고 검증하는 방법을 배우고, 검증된 HashiCorp 도구가 포함된 사용자 지정 리눅스 컨테이너를 생성할 수 있습니다.

> ## FreeBSD
>
> ### 바이너리 파일 다운로드
>
> [386](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_freebsd_386.zip)
>
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_freebsd_amd64.zip)
>
> [ARM](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_freebsd_arm.zip)

> ## OpenBSD
>
> [386](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_openbsd_386.zip)
>
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_openbsd_amd64.zip)

> ## Solaris
>
> [AMD64](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_solaris_amd64.zip)

## 출시 정보

> ### [변경 내역](https://github.com/hashicorp/terraform/releases/tag/v1.10.5)
>
> 테라폼 버전: 1.10.5

> ### [공식 출시](https://www.hashicorp.com/official-release-channels)
>
> 공식적으로 지원되는 모든 HashiCorp의 출시 채널과 보안 보증

> ### 참고
>
> <!-- TODO Link the tutorial document after translating it -->
> [테라폼 1.10.5의 SHA256 체크섬](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_SHA256SUMS)을 온라인에서 확인할 수 있고, [HashiCorp의 GPG 키](https://www.hashicorp.com/security)로 서명된 [체크섬 서명 파일을 검증](https://releases.hashicorp.com/terraform/1.10.5/terraform_1.10.5_SHA256SUMS.sig)할 수 있습니다. 이 [튜토리얼](https://developer.hashicorp.com/well-architected-framework/operational-excellence/verify-hashicorp-binary)을 완료하여 모든 리눅스 배포판에서 HashiCorp 도구를 설치하고 검증하는 방법을 배워 보세요.

---

### [테라폼 공식 문서](https://developer.hashicorp.com/terraform/install)

**마지막 업데이트:** 2025년 1월 24일