[!INCLUDE [header_file](../../../includes/sol-idea-header.md)]

With Speech services, it's easy to transcribe every call. Index the transcription for [full-text search](/azure/search/search-what-is-azure-search), or apply [Text Analytics](/azure/cognitive-services/Text-Analytics) to detect sentiment, language, and key phrases for insights. If your call center recordings involve specialized terminology, such as product names or IT jargon, create a custom [language model](/azure/cognitive-services/speech-service/how-to-customize-language-model) to teach Speech Services the vocabulary. A custom [acoustic model](/azure/cognitive-services/speech-service/how-to-customize-acoustic-models) helps Speech Services understand speakers even with background noise or poor phone connections.

For more information, read how [batch transcription](/azure/cognitive-services/speech-service/batch-transcription) works with Speech Services.

## Potential use cases

This solution can be for organizations that record conversations (for training or quality assurance) that also want a written transcript. It's ideal for the education, retail, and nonprofit industries.

## Architecture

![Architecture diagram shows recorded calls to Azure Trans Queue to Speech Endpoint to Transcription Result Queue to Transcript Blob and Insights.](../media/speech-services.png)
*Download an [SVG](../media/speech-services.svg) of this architecture.*

### Dataflow

1. Adapt a model for your domain and deploy that model.
1. Upload your recordings to a blob container.
1. Create a POST request to batch transcription.
1. The Speech service schedules the transcription job.
1. Stereo files are split into two channels.
1. Mono files undergo diarization to distinguish between speakers.
1. Download the transcription using the transcription ID.

### Components

* [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs)
* [Speech service](https://azure.microsoft.com/en-us/services/cognitive-services/speech-services)

## Next steps

To learn more about these services, see the following articles:

* [Azure Blob Storage](/azure/storage/blobs)
* [Speech service](/azure/cognitive-services/Speech-Service)

## Related resources

* [Artificial intelligence (AI) - Architectural overview](../../data-guide/big-data/ai-overview.md)
* [Speech-to-text conversion](../../reference-architectures/ai/speech-to-text-transcription-pipeline.yml)
