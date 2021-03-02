[공통] SFP-CORE
======================

# 1. sfp-core 개요
## 1.1. sfp-core 란?
sfp-core는 서비스 개발의 편의성을 위한 개발 프레임웍크다. jpa, mybatis 및 기타 기능을 제공한다.

## 1.2. sfp-core
### * 기능 개요
	1. crud 관련 기본 메소드 제공.
	2. 메세지 이벤트를 통한 디커플링.
	3. 업무시간에 따른 스케쥴링.
	4. 대용량 엑셀 다운로드등의 유틸제공.
	5. 스프링 부트 주요설정은 기본으로 설정됨.
	
# 2. package 구조
<!--
![패키지 구조]("https://218.155.198.200:3980/svn/FRAMEWORK/!svn/ver/2759/SFP/sfp-core/trunk/doc/images/package.png")
-->

## 2.1. com.s3s.sfp.define
공통 이벤트 정의 및 enum 에 대한 정의가 있다.

## 2.2. com.s3s.sfp.exception
RuntiemException 을 상속한 sfp 공통 exception 정의되어 있으며, 프로젝트의 runtime exception 은 해당 exception 을 상속해서 throws 하면 화면이 구현된 경우 화면에 표시된다.

* Example
    ```
   throw new SFPException(화면에 표시될 message);
    ```

## 2.3. com.s3s.sfp.manager
### 2.3.1. com.s3s.sfp.manager.decision


### 2.3.2. com.s3s.sfp.manager.memory


### 2.3.3. com.s3s.sfp.manager.message


### 2.3.4. com.s3s.sfp.manager.task

## 2.3. com.s3s.sfp.security
권한사용시에 필요한 클래스들이 존재하며, 해당 클래스는 [**sfp-core-security**](https://218.155.198.200:3980/!/#FRAMEWORK/view/head/SFP/sfp-core-security) 에서 사용됨

## 2.3. com.s3s.sfp.service
### 2.3.4. com.s3s.sfp.service.jpa
jpa .. 메소드들 설명필요

### 2.3.4. com.s3s.sfp.service.mybatis
mybatis 메소드들 설명필요


## 2.3. com.s3s.sfp.settings


## 2.3. com.s3s.sfp.support


* ExcelDownTools
    ```java
   @PostMapping("url~~")
	public ResponseEntity<?> downloadExcel(HttpServletResponse response, 검색조건 dto, ExcelDTO excel){
		ExcelDownTools.downExcel(response, 조회한 list, excel);
		return ResponseEntity.ok().build();
	}
    ```
