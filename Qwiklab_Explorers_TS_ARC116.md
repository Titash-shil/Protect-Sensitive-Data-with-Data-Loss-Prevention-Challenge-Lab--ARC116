# Protect Sensitive Data with Data Loss Prevention: Challenge Lab || [ARC116](https://www.cloudskillsboost.google/focuses/64782?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

## Run the following commands in CloudShell and follow video:

```
export BUCKET_NAME=
```

```
gcloud auth list

gcloud config set project $DEVSHELL_PROJECT_ID


cat > redact-request.json <<EOF_CP
{
	"item": {
		"value": "Please update my records with the following information:\n Email address: foo@example.com,\nNational Provider Identifier: 1245319599"
	},
	"deidentifyConfig": {
		"infoTypeTransformations": {
			"transformations": [{
				"primitiveTransformation": {
					"replaceWithInfoTypeConfig": {}
				}
			}]
		}
	},
	"inspectConfig": {
		"infoTypes": [{
				"name": "EMAIL_ADDRESS"
			},
			{
				"name": "US_HEALTHCARE_NPI"
			}
		]
	}
}
EOF_CP


curl -s \
  -H "Authorization: Bearer $(gcloud auth print-access-token)" \
  -H "Content-Type: application/json" \
  https://dlp.googleapis.com/v2/projects/$DEVSHELL_PROJECT_ID/content:deidentify \
  -d @redact-request.json -o redact-response.txt


gsutil cp redact-response.txt gs://$BUCKET_NAME


echo "Please subscribe to techcps[https://www.youtube.com/@techcps]"

echo "Click the below link"

echo "-------------"

echo "Click here to open the link https://console.cloud.google.com/security/sensitive-data-protection/landing/configuration/templates/inspect?cloudshell=true&project=$DEVSHELL_PROJECT_ID"

```

- ## Follow next steps carefully from the video 

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
