# VideoDB Understanding guides

Create reusable, timestamped facts from video and audio, then decide which facts should be retrievable.

```text
Video → Understand → Artifacts → Index → Retrieve
```

- **Understanding** runs analyzers and stores timestamped artifacts: speech, visible text, objects, brands, activities, locations, or custom VLM output.
- **Indexing** chooses which artifact fields support semantic search, exact filters, aggregation, and sorting.
- **Retrieval** returns matching moments, analytics, or grounded answers from those indexes.

A VLM is a **vision-language model**. Use a dedicated analyzer when you need a standard output such as OCR or object detections; use a VLM when you need a custom prompt or schema.

## Recommended path

1. Start with the [Understanding quickstart](quickstart.ipynb).
2. Open one analyzer guide for the signal you need.
3. Use [Segmentation and sampling](segmentation-and-sampling.ipynb) to tune time ranges and frame coverage.
4. Use [Multi-analyzer pipelines](multi-analyzer-pipelines.ipynb) only when a downstream analyzer needs transcript, OCR, or object context.
5. Turn the resulting artifacts into retrieval-ready fields with the [Indexing guide](../indexing/indexing_guide.ipynb).
6. Choose direct or intelligent retrieval in the [Search V2 guide](../search/search_guide.ipynb).

For one runnable path through all three stages, use the [complete Indexing V2 quickstart](../quickstart.ipynb).

## Analyzer guides

| Goal | Analyzer | Guide | Compute |
|---|---|---|---|
| Search what was said | `spoken_words` | [Speech transcription](speech-transcription/speech-transcription.ipynb) | Managed |
| Locate and count known object classes | `object_detection` | [Object detection](object-detection/object-detection.ipynb) | Sandbox |
| Read visible text | `ocr` | [OCR](ocr/ocr.ipynb) | Managed |
| Find visible brands | `brand_detection` | [Brand detection](brand-detection/brand-detection.ipynb) | Managed |
| Describe actions | `activity_recognition` | [Activity recognition](activity-recognition/activity-recognition.ipynb) | Managed |
| Describe settings | `location_detection` | [Location detection](location-detection/location-detection.ipynb) | Managed |
| Extract custom visual fields | `vlm` | [Managed Models](vlm/managed-models.ipynb) · [Sandbox Models](vlm/sandbox-models.ipynb) | Managed or sandbox |

## Concepts and operations

- [Understanding quickstart](quickstart.ipynb) — the smallest speech + vision run
- [Segmentation and sampling](segmentation-and-sampling.ipynb) — scene boundaries and frame selection
- [Multi-analyzer pipelines](multi-analyzer-pipelines.ipynb) — dependencies and aligned context
- [Outputs and operations](outputs-and-operations.ipynb) — statuses, polling, callbacks, resume, validation, and cleanup

## From artifacts to retrieval

- [Indexing guide](../indexing/indexing_guide.ipynb) — index analyzer artifacts
- [Custom index guide](../indexing/custom_index.ipynb) — index your own timestamped records
- [Search V2 guide](../search/search_guide.ipynb) — search, query, aggregate, DeepSearch, Ask, and playback
- [Complete Indexing V2 quickstart](../quickstart.ipynb) — Understand → Index → Retrieve in one notebook

The canonical Understanding notebooks live in this directory. Older preview copies should not be updated independently.
