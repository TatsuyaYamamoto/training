### https://api.twitter.com/oauth/request_token

- oauth_callback
	- 「Callback URL」に設定したURLアドレスを指定する。認証画面で作業を終えたユーザーが戻ってくるURLアドレス。
- oauth\_consumer_key(☆)
	- アプリケーション作成時に取得したAPI Key。
- oauth\_signature_method(☆)
	- 署名の種類を指定。HMAC-SHA1を指定すればいい。
- oauth_signature(☆)
	- 作成した署名を指定する。
- oauth_timestamp(☆)
	- リクエストを送る際のUNIX TIMESTAMPの値を指定する。具体的には、PHPでtime()の値をそのまま指定すればいい。
- oauth_nonce(☆)
	- 任意で用意したランダムな文字列を指定する。PHPなら、例えばmicrotime()などの値をそのまま指定すればいい。
- oauth_version(☆)
	- 認証に利用する規格であるOAuthのバージョンを指定する。1.0を指定すればいい。







### https://api.twitter.com/oauth/access_token


- oauth\_consumer_key(☆)
	- アプリケーション作成時に取得したAPI Key。
- oauth_token
	- ユーザーが認証作業を終えて戻ってきた時、URLに付けているパラメータのoauth_tokenの値。
- oauth\_signature_method(☆)
	- 署名の種類を指定。HMAC-SHA1を指定すればいい。
- oauth_signature(☆)
	- 作成した署名を指定する。
- oauth_timestamp(☆)
	- リクエストを送る際のUNIX TIMESTAMPの値を指定する。具体的には、PHPでtime()の値をそのまま指定すればいい。
- oauth_verifier
	- ユーザーが認証作業を終えて戻ってきた時、URLに付けているパラメータのoauth_verifierの値。
- oauth_nonce(☆)
	- 任意で用意したランダムな文字列を指定する。PHPなら、microtime()の値をそのまま指定すればいい。
- oauth_version(☆)
	- 認証に利用する規格であるOAuthのバージョンを指定する。1.0を指定すればいい