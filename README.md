# 💸 Giveable

**Workplace payroll giving for local charities in Canada.** Employees give to CRA-registered charities straight from their paycheque. Employers get a simple way to support their community, and charities get steady, recurring donations.

> Solo-founded and built by [Israel Snowe](https://github.com/israelsnowepm), a Senior PM. The application code is in a private repo. This page covers the product.

---

## The problem

Most workplace giving tools are built for large enterprises and national charities. Small and mid-sized Canadian employers have no easy way to offer payroll giving, and local charities miss out on the most reliable kind of donor: the recurring one.

## How it works

1. **The employer joins** and invites its team.
2. **Employees choose** a local charity and an amount per pay period.
3. **Giveable calculates the deduction** and sends the funds to each charity through Stripe Connect, on a schedule.
4. **The charity issues the tax receipt.** Giveable sends it everything it needs for CRA receipting.

## Product decisions

- **Impact in meals, not dollars.** Donors see "12 meals funded" rather than "$30." It's more concrete and more motivating.
- **A shared goal instead of a leaderboard.** I cut the leaderboard and replaced it with a Collective Goal Bar. Ranking coworkers by how much they give works against why people give.
- **An impact email instead of an employer portal.** I cut the self-serve employer dashboard from v1 and replaced it with a generated Employer Impact Email. It delivers the same value for far less build and maintenance.
- **Charities issue receipts.** This keeps Giveable out of the receipting liability and respects the CRA rules charities already follow.
- **Provincial edge cases are handled explicitly.** Quebec needs separate handling, and the design accounts for it.

## Stack

Next.js · Vercel · Supabase · Stripe Connect · PostHog · Resend · Sentry

## How I build

- **Spec-first.** The PRD went through v1.6 before a feature was built, and every cut above is a documented decision.
- **AI-native development.** I use Claude Code as the primary builder and Cursor to review pull requests.
- **Risk-focused review.** Every PR goes through a review prompt written for this project. It checks for Supabase row-level security gaps, Stripe Connect edge cases and donor-data exposure.

## Status

Pre-revenue. Validation so far:
- Conversations with Winnipeg charities, two of which said a soft yes
- The model reviewed with a retired CEO of a Canadian payroll company
- Legal counsel engaged

---

📧 israelsnowe.pm@gmail.com · 💼 [linkedin.com/in/israel-snowe](https://linkedin.com/in/israel-snowe)
