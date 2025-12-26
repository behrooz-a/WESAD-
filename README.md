# WESAD-
To access the dataset, it is required to reach out https://www.kaggle.com/datasets/orvile/wesad-wearable-stress-affect-detection-dataset.

The data has been converted by notebooks_wesad file from PKL format to parquet and downsampled from 700 Hz to 250 Hz.

Polyphase downsampling is an efficient method for changing the sampling rate of a signal by a rational factor. It works by first upsampling the signal, applying a zero-phase low-pass FIR filter to prevent aliasing, and then downsampling to the target rate. Instead of performing all computations on the full upsampled signal, the filter is decomposed into polyphase components, which significantly reduces computational cost. This approach is ideal for non-integer resampling ratios, such as converting 700 Hz data to 250 Hz, because it preserves signal integrity while minimizing distortion and aliasing.

The Polyphase downsampling provides two main advantages: it is computationally efficient and preserves signal quality. 

Efficiency: By cleverly rearranging the anti-aliasing filter into subfilters, it only calculates output samples that are actually saved rather than processing data that would be discarded during decimation.

Signal Integrity: It operates the filter at the lowest possible rate—the final output rate—while using high-performance FIR filters to prevent aliasing and maintain a linear phase response. 

