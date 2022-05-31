---
title: 2021-javascript-jquery-study
toc: true
---

# 2021-javascript-jquery-study

This repository is repository about javascript and jquery study.



## 목차

[TOC]




### 01 중첩함수 관련(369p)

<- 화살표로 표시된 부분을 참고하자 중첩 함수에서 $(this)가 어떻게 사용되는지 이해하면될 것 같다.

```
function tabMenu(selector){
   var $tabMenu = null;
   var $menuItems = null;
   // 선택 한 탭메뉴를 저장할 변수
   var $selectMenuItem =null;

   init(selector);
   initEvent();

   function init(selector) {
      // 요소 초기화
      $tabMenu = $(selector);
      $menuItems = $tabMenu.find("li");
   }

   function initEvent() {
      // 메뉴 항목에 클릭 이벤트 등록
      $menuItems.click(function(){
         selectTab($(this)); <- 다음과 같이 $(this)를 주어 어떤 개체를 선택할 수 있는 구분자를 매개변수로 전달한다
      })

   }

   function selectTab($item) { <- $(this)를 argument로 받음
      // 기존 선택 메뉴 항목이 있으면 비선택 상태로 만들기
      if($selectMenuItem!=null){
         $selectMenuItem.removeClass("select");
      }

      // 클릭한 메뉴 항목을 신규 선택 메뉴 항목으로 저장
      $selectMenuItem = $item; <- $(this)를 저장해서 내가 선택한 개체를 제어할 수 있게 함
      // 선택 상태로 만들기
      $selectMenuItem.addClass("select"); <- 다음 함수는 $(this) 개체에 select 클래스를 추가 함
   }
}
```
