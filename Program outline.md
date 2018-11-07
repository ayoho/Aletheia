= Program steps

1. Audio input


2. Send to rev.ai

    URL:
        curl -X POST "https://api.rev.ai/revspeech/v1beta/jobs" -H "Authorization: Bearer <api_key>" -H "Content-Type: application/json" -d "{\"media_url\":\"https://support.rev.com/hc/en-us/article_attachments/200043975/FTC_Sample_1_-_Single.mp3\",\"metadata\":\"This is a sample submit jobs option\"}"
    Local file:
        curl -X POST "https://api.rev.ai/revspeech/v1beta/jobs" -H "Authorization: Bearer <api_key>" -H "Content-Type: multipart/form-data" -F "media=@/path/to/media_file.mp3;type=audio/mp3" -F "options={\"metadata\":\"This is a sample submit jobs option for multipart\"}"

    Response:

        {"id":"2028247","created_on":"2018-09-15T05:14:38.13","name":"sample.mp3","metadata":"This is a sample submit jobs option for multipart","status":"in_progress"}

3. Get transcript

    curl -X GET "https://api.rev.ai/revspeech/v1beta/jobs/{id}/transcript" -H "Authorization: Bearer <api_key>" -H "Accept: application/vnd.rev.transcript.v1.0+json"

4. Compile transcript back into sentence strings


5. Extract factual statements from sentences


6. Retrieve facts relating to statements


7. Verify the facts in the statements
