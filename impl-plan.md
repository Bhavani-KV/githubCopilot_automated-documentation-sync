# Implementation Plan

## Prioritized Dependency-Ordered Tasks

1. **Create the standalone HTML page**
   - Add the tracking-number input, **Track** button, result area, and error message area.
   - **Dependencies:** None.

2. **Add the in-memory mock data**
   - Define the four required tracking numbers and statuses:
     - `TRK-1001` - Order Received
     - `TRK-1002` - In Transit
     - `TRK-1003` - Out for Delivery
     - `TRK-1004` - Delivered
   - **Dependencies:** Task 1 is not required for data definition, but this must be available before lookup wiring.

3. **Implement tracking lookup behavior**
   - Run only when the user clicks **Track**.
   - Trim leading and trailing spaces.
   - Keep matching case-sensitive.
   - Treat an empty value after trimming as not found.
   - **Dependencies:** Tasks 1 and 2.

4. **Implement result and error rendering**
   - For a match, display both the tracking number and current delivery status.
   - For an unknown or empty tracking number, display the same error message.
   - **Dependencies:** Tasks 1 and 3.

5. **Add minimal page styling**
   - Style the standalone page and its required controls and states without external dependencies.
   - **Dependencies:** Task 1.

## Blocked Tasks

- None. All design decisions required for implementation have been resolved.
