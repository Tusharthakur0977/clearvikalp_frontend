# 🏥 ClearVikalp - Medical Test Booking Platform

A high-performance, conversion-optimized frontend application designed to streamline the booking process for medical tests and lab services. Built with a focus on marketing attribution tracking, responsive design, and seamless user experience.

## 🚀 Tech Stack

*   **Core Framework**: React 18, TypeScript
*   **Routing**: React Router DOM
*   **State Management**: React Context API
*   **Styling & UI**: Tailwind CSS, Material UI (`@mui/material`), Material-Tailwind, Emotion
*   **Analytics & Tracking**: Google Tag Manager (`react-gtm-module`)
*   **Component Libraries**: React Slick (Carousels), React Dropdown, React Icons
*   **API Communication**: Fetch API (Native), Axios

## ⭐ Spotlight Feature: Dynamic Marketing Attribution & Global Booking State

**The Challenge:**
In modern healthcare marketing, accurately attributing leads to specific ad campaigns is critical. The application needed to capture extensive URL parameters, persist them globally without cluttering component props, and attach them reliably to user booking submissions and analytics events—all while handling complex form validation and asynchronous API states.

**Under the Hood:**
*   **URL Parameter Interception:** `App.tsx` utilizes `useSearchParams` to intercept 14 distinct marketing parameters (including `campaignid`, `gclid`, `utm_source`, `matchtype`, etc.) upon initial load.
*   **Global Context Management:** These parameters are immediately injected into a global `BookModalContext` alongside the booking flow states (`isBookModal`, `isFormFilled`, `selectedPLan`). This avoids prop-drilling and ensures the data is accessible everywhere.
*   **Context-Aware Booking Engine:** Inside `BookingCard.tsx`, the form validation logic seamlessly accesses this context. Upon submission, it constructs a robust payload combining the user's details, the selected lab partner, and the exact marketing parameters.
*   **Dynamic Analytics Tracking:** Simultaneously, the component manually pushes customized events (`booking_card_submit`) to the GTM `dataLayer`, distinguishing whether the user converted from a popup card or a static page card.

**Why it's impressive:**
This feature bridges the gap between complex marketing requirements and solid React architecture. It handles asynchronous side-effects, complex form state (validation, loading, success views), and third-party tracking APIs within a clean, centralized Context provider, ensuring the codebase remains maintainable and highly scalable.

## 🛠 Features

*   **Responsive Landing Page Architecture**: Modular sections (`Hero`, `Plans`, `StepsJourney`, `FAQ`, `Accreditation`) built with Tailwind CSS to ensure a pixel-perfect experience across all devices.
*   **Contextual Booking Modals**: A global `BookTestModal` that can be triggered from multiple touchpoints (like the `StickyButton`), providing a frictionless conversion funnel.
*   **Dynamic Lab Selection**: Integrated custom dropdowns for selecting preferred lab partners (e.g., Metropolis, Redcliffe, Manipal TRUtest) with robust form validation.
*   **Smooth Carousels & Animations**: Implemented slick carousels for test plans and reviews, ensuring an engaging and interactive user interface.

## 💡 Why This Project Stands Out

This project demonstrates my ability to build frontend applications that are not just visually appealing, but functionally robust and business-oriented. By engineering a custom solution for marketing attribution and integrating it deeply with a global React Context state, I successfully addressed a complex real-world business requirement. The codebase showcases a strong understanding of TypeScript, component reusability, form lifecycle management, and the integration of third-party analytics, proving my capacity to deliver production-ready, scalable web applications.
