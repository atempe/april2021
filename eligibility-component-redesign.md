# Eligibility Checker Component Redesign

## Goal
Make it immediately obvious whether a customer is eligible by reducing visual noise and prioritizing a clear status outcome.

## Simplified UX

### 1) Move eligibility card above the fold
Place a single, focused card directly under the page heading.

**Card title:** `Check your eligibility`

**Supporting text:** `Enter your work or school email to instantly see if you qualify.`

### 2) One input + one primary action
- **Input label:** `Work or school email`
- **Placeholder:** `name@company.com`
- **Primary button:** `Check eligibility`

Remove extra wording like domain/id examples from the main flow. Put examples in helper text.

### 3) Clear, high-contrast result state (most important)
Show result in a dedicated result panel right below the button.

#### Eligible state
- Icon: ✅
- Title: `You're eligible`
- Message: `Your organization qualifies for [Program Name].`
- CTA: `Continue`

#### Not eligible state
- Icon: ❌
- Title: `Not eligible right now`
- Message: `We couldn't find an eligible organization for this email.`
- CTA 1: `Try another email`
- CTA 2 (secondary): `See all offers`

#### Error state
- Icon: ⚠️
- Title: `We couldn't check eligibility`
- Message: `Please try again in a moment.`
- CTA: `Try again`

### 4) Reduce competing navigation
In this section, hide or de-emphasize secondary tabs (`Register`, `Offer Programs`) until after eligibility is confirmed.

### 5) Add progress clarity
Replace “Step 1” text with compact progress indicator:

`Step 1 of 2: Eligibility` → `Step 2 of 2: Verification`

## Suggested component structure

```txt
EligibilitySection
  Heading
  EligibilityCard
    EmailInput
    CheckEligibilityButton
    EligibilityResult
      StatusIcon
      StatusTitle
      StatusMessage
      PrimaryCTA
      SecondaryCTA (optional)
```

## Example microcopy

- Heading: `Check your eligibility`
- Subtext: `Use your work or school email.`
- Eligible result: `Great news — you're eligible for Employee Offers.`
- Not eligible result: `This email isn't in an eligible organization yet.`

## Accessibility requirements

- Announce result changes with `aria-live="polite"`.
- Focus the result container after check submission.
- Ensure eligible/not-eligible status is not color-only (include icon + text).
- Input and button must be fully keyboard operable.

## Success metric

- Increase users who complete eligibility check in first attempt.
- Reduce time-to-understand result to under 3 seconds after response appears.
