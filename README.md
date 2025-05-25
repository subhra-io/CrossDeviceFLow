Verifier User visits the Verifier Web App and initiates a request.
Web App sends a POST to /"COMPANY NAME"/openid/par with a client JWT.
Cloud Agent validates the JWT, generates an Authorization Request JWT, and returns a request_uri.
Web App generates a QR code with openid4vp://authorize?request_uri=....
Holder User scans the QR code with the wallet.
Wallet fetches the Authorization Request from /"COMPANY NAME"/openid/request/:id, validates it, matches HOLDERS credentials, and gets user consent.
Wallet submits the vp_token to /"COMPANY_NAME"/openid/callback.
Cloud Agent validates the vp_token, encrypts user data, stores it, and notifies the Web App.
Web App grants access to the Verifier User.