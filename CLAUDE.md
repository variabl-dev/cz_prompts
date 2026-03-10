# cz_prompts

Project containing AI prompts for various workflows.

## Generating n8n nodes

To generate an n8n "Execute Workflow" node that calls the "Call Ai" workflow with a prompt file, use this template:

```json
{
  "nodes": [
    {
      "parameters": {
        "workflowId": {
          "__rl": true,
          "value": "K6Llp9nFrwUnUWFk",
          "mode": "list",
          "cachedResultUrl": "/workflow/K6Llp9nFrwUnUWFk",
          "cachedResultName": "Call Ai"
        },
        "workflowInputs": {
          "mappingMode": "defineBelow",
          "value": {
            "prompt file path": "<PATH>",
            "text": "={{$json.text?.toJsonString()}}"
          },
          "matchingColumns": [],
          "schema": [
            {
              "id": "text",
              "displayName": "text",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "canBeUsedToMatch": true,
              "type": "string",
              "removed": false
            },
            {
              "id": "structure",
              "displayName": "structure",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "canBeUsedToMatch": true,
              "type": "string",
              "removed": true
            },
            {
              "id": "prompt file path",
              "displayName": "prompt file path",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "canBeUsedToMatch": true,
              "type": "string",
              "removed": false
            }
          ],
          "attemptToConvertTypes": false,
          "convertFieldsToString": true
        },
        "options": {}
      },
      "type": "n8n-nodes-base.executeWorkflow",
      "typeVersion": 1.3,
      "position": [
        1296,
        -752
      ],
      "id": "<GENERATE_UUID>",
      "name": "<NODE_NAME>"
    }
  ],
  "connections": {},
  "pinData": {},
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "5f8e866bc1937ddf49e98dbdc9aa180a1c4240a9c869c3bcecf289e9b34fb13f"
  }
}
```

Replace:
- `<PATH>` - path to the prompt file (e.g., `accounts payable/Incomming mail categorizer.md`)
- `<GENERATE_UUID>` - generate a new UUID
- `<NODE_NAME>` - descriptive name for the node (e.g., `Categorize Invoice`)
