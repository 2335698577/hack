# Loop progress

Updated 14 November 2026 (UK time).

Loop is our DurHack project for anonymous peer help. A participant requests help, another accepts, the robot delivers a paper note, and time credits settle after completion.

## Member B progress

- Installed Node.js 24 via nvm and Firebase CLI 15.36.0. Google sign-in through the CLI succeeded.
- Enabled Anonymous Authentication and registered the practice web app.
- Created the English practice page and fixed its duplicate Firebase configuration declaration. The test button now opens for use.
- Still to verify: the Firestore database was created and the browser completed anonymous sign-in, wrote a dummy record, and read it back from the server.

## Run the Firebase practice test

1. In a separate practice project, enable Anonymous Authentication, create Firestore, and register a Web app.
2. Copy [the practice page](../practice/index.html) into a local folder. Replace the entire `const firebaseConfig = {};` declaration with the Web app configuration from Firebase Project settings.
3. In that folder, run `python3 -m http.server 8000 --bind 127.0.0.1` and open `http://127.0.0.1:8000/index.html`.
4. Click **Test sign-in and database**. Look for **Anonymous sign-in successful** and **Read from Firestore: Hello Loop**. Compare the displayed document ID with Firestore Data → `practice`.

## Next steps

- Member A owns the phone interface, dispatch console, and robot. Member B owns Firebase, the time-credit ledger, matching, and statistics.
- Agree who must select **Done** before credits settle. The written ledger calls for confirmation by both participants, while the phone flow shows the requester selecting Done.
- Agree on the request and dispatch fields. A dispatch task should visit the requester first and the helper second.
- Test the full flow on two phones. With both participants starting at 3 credits and the request priced at 1 credit, the final balances should be 2 and 4.
- Record milestones and test results in GitHub. Use English in the UI, repository, and DurHack submission.
