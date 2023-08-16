Steps to reproduce

Create a KMS key for sops to use in your AWS acc.

Encrypt the secrets.dec.yaml file with sops (using your KMS key ARN) and write to secrets.yaml
`$ cd realm/namespaces/myNs/services`
`$ sops --kms "arn:aws:kms:eu-west-1:0922340834:key/23lk4j234-0444-4444-k44-3234lkj234" -e ../../../values/env/myEnv/secrets.dec.yaml > ../../../values/env/myEnv/secrets.yaml`

Try to template out
`$ helmfile --environment myEnv --file my-release.yaml template`