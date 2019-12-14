---
layout: default
title: WSL2 with Docker
categories: category
permalink: path
tags: tag
excerpt: description
---

# WSL2 docker backend

WSL2 를 윈도우에서 발표하면서 docker의 구동 방식에도 변경이 있었다. 지금 윈도우 10은 WSL1을 정식 지원하고 있다.
WSL1 은 리눅스의 모든 기능을 가상화하진 않는다. WSL1 과 WSL2 의 차이는 나중에 알아보기로 하고 우선 WSL2 활성화와 docker backend 에 대해 정리한다.

## WSL2 활성화
아직 preview 기능이므로 window 10 의 insider preview 를 활성화하여 최신 빌드를 설치한다.
> WSL2는 18917부터 활성화가 가능한데 docker WSL2 backend 는 19018 이상을 요구한다.(이유는?)

### 활성화 키워드
> https://docs.microsoft.com/en-us/windows/wsl/wsl2-install

```PowerShell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
기능을 활설하고 재부팅을 해야 한다.

```
wsl --set-default-version 2
```
모든 배포판을 wsl2 로 설정한다.

