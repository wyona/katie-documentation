---
sidebar_label: 'Katie for FAQ'
sidebar_position: 3
---

# Katie for FAQ

## About

This documentation explains how to make your FAQ (managed by Katie) available on your website or whatever channel you would like your FAQ to be available.

Examples are

* https://www.copine.ch/faq
  * https://ukatie.com/#/faq/c9af3861-68cc-4872-b966-4bd19f3d4df7/de
* https://lucene-faq.ukatie.com/
  * https://ukatie.com/#/faq/9f206aec-5223-4e03-a2fc-c16e4b885ef8/en

Additional resources are

* https://ukatie.com/katie4faq.html
* https://github.com/wyona/katie-4-faq

## Basic Website Visitor BDD Scenarios

### Display FAQs

* *GIVEN* I have a domain (e.g. 9f206aec-5223-4e03-a2fc-c16e4b885ef8) at Katie and I have entered several QnAs for a particular language, e.g. https://ukatie.com/#/faq/9f206aec-5223-4e03-a2fc-c16e4b885ef8/en
* *WHEN* I open the FAQ page of my website which is integrated with Katie
* *THEN* the FAQs are being retrieved from Katie and displayed in my own design.

## Ask question

* *GIVEN* I am on the FAQ page of my website and it provides a search input field to enter a question
* *WHEN* I enter a question
* *THEN* the question will be submitted to Katie and Katie's answer will be displayed

### Send question to expert

* *GIVEN* I am on the FAQ page of my website and it provides a search input field to enter a question
* *WHEN* I enter a questions, but Katie does not have an answer or Katie's answer is not helpful
* *THEN* I can enter my email address and the question together with my email address is submitted to Katie, where a human expert is notified to answer my question

### i18n

* *GIVEN* my website is providing the FAQ in multiple languages (e.g. english, german, and portuguese)
* *WHEN* I open the FAQ page for a particular language
* *THEN* beside the FAQ content itself, also all the other texts (e.g. labels of UI elements such as cancel or submit button) have to be displayed in this language

## Basic Back-end Requirements

### Katie integration/connection configuration

* One has to be able to set/configure the Katie Domain Id, e.g. 9f206aec-5223-4e03-a2fc-c16e4b885ef8
* One has to be able to set/configure the FAQ language per page, e.g.
  * DE: https://rockondigital.ch/haeufig-gestellte-fragen/
  * EN: https://rockondigital.ch/frequently-asked-questions/

### Configure/Customize Design

* The integration of the FAQ should work like embedding a component, which means the global design of the website (e.g. https://rockondigital.ch/) is being applied.
* The design of the various UI elements of the FAQ component should be customizable and not conflict with the global UI elements, e.g. https://github.com/wyona/katie-4-faq/blob/main/clients/katie4faq-js/src/katie-style.css

## Technical Documentation - REST Interfaces

The REST Interfaces of Katie are documented by Swagger: https://ukatie.com/swagger-ui/

## Get all FAQs

See https://ukatie.com/swagger-ui/?urls.primaryName=API%20V2#/faq-controller-v-2/getFAQUsingGET_1

whereas try with the following parameters

* context/domain Id: 9f206aec-5223-4e03-a2fc-c16e4b885ef8
* language: en
* uuid-only: false

## Ask question

See https://ukatie.com/swagger-ui/#/ask-controller/getAnswerUsingGET

whereas try with the following parameters

* domainId: 9f206aec-5223-4e03-a2fc-c16e4b885ef8
* question: How do I start using Lucene?

## Send question to expert

See https://ukatie.com/swagger-ui/#/ask-controller/getAnswerUsingGET

whereas try with the following parameters

* domainId: 9f206aec-5223-4e03-a2fc-c16e4b885ef8
* question: How do I start using Lucene?
* email: Your own email address, e.g. michael.wechner@wyona.com