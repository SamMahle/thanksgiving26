# Thanksgiving "Now / Next" kitchen display

Single-page kitchen display for Thursday 11/26/2026. It shows the current and next cooking steps from the device clock and syncs checkmarks and delays across devices through Firebase Realtime Database.

- `index.html`: the whole app. The Firebase web config is inline near the top of the script. It isn't secret; the database rules protect the data.
- `database.rules.json`: Realtime Database rules, for reference. Allows read and write only under `/thanksgiving`, and writes stop at the end of 11/28/2026 (ET).

Shared state is stored at `/thanksgiving/state` as `{ done: { [stepIndex]: true }, shifts: [ { from, mins } ] }`.
