# Design Review

## Review Summary

The proposed architecture is appropriately small and consistent with `requirements.md`. It uses a standalone client-side page, in-memory mock data, vanilla JavaScript, and no unnecessary frameworks, services, or dependencies. All stated requirements are represented in the architecture.

No high- or medium-severity requirement mismatches were found. The two low-severity behavior details have been resolved.

## Findings

### 1. Input normalization is resolved

- **Category:** Design decision to clarify
- **Severity:** Low
- **Finding:** The requirements did not specify how whitespace and letter casing should be handled.
- **Resolution:** Trim leading and trailing spaces from the entered tracking number, then match it case-sensitively.
- **Recommended action:** Implement the resolved input handling.

### 2. Empty input behavior is resolved

- **Category:** Design decision to clarify
- **Severity:** Low
- **Finding:** The requirements did not specify what happens when the user submits an empty tracking number.
- **Resolution:** If the tracking number is empty after trimming, show the same error message used for an unknown tracking number.
- **Recommended action:** Implement the resolved empty-input behavior.

## Recommended Actions

1. Implement trimming of leading and trailing spaces while keeping matching case-sensitive.
2. Show the existing unknown-tracking-number error when the trimmed input is empty.
3. Keep the current architecture unchanged for the remaining requirements; it is sufficient for the stated scope.

## Agreed Design Decisions

- The tracker will be a standalone client-side web page.
- The tracker will use HTML, CSS, and vanilla JavaScript only.
- Delivery data will be held in an in-memory mock data store.
- The mock data will include `TRK-1001`, `TRK-1002`, `TRK-1003`, and `TRK-1004` with the four required statuses.
- A lookup will occur when the user clicks **Track**.
- A successful lookup will display both the tracking number and its current delivery status.
- An unknown tracking number will display an error message.
- Leading and trailing spaces will be trimmed from the entered tracking number.
- Tracking-number matching will remain case-sensitive.
- An empty tracking number after trimming will display the same error message as an unknown tracking number.
- No backend, database, external API, framework, or additional dependency is needed.
