# Alpha oscillatory profiles in autistic children

## Description

The main goal of this project is to define how different patterns of periodic and aperiodic EEG activity are associated with different developmental profiles in autistic children. After datapreprocessing, we applied here an algorithm for the explicit parameterization of neural power spectra (Donoghe et al. 2020) to resting-state EEG data of autistic and control children.

This spectral parameterization ("specparam", https://github.com/fooof-tools/fooof ) algorithm fits components of power spectral densities (PSDs) in a way that is informed by physiology, without relying on predefined canonical frequency bands. This method has recently been introduced in pediatric research as a promising approach for addressing inter-individual differences in power spectra and for elucidating the role of aperiodic activity in various cognitive processes (Ostlund et al., 2022).

Here, starting from the output of specparam, I organized data in a unique dataset and performed some preliminary visualizations and statistical analyses to test the answer these research questions:
1. Are there differences in alpha amplitude and aperiodic slope between ASD and TD subjects?
2. Is there an association in autism between alpha amplitude and cognitive development (Wang et., 2013, Mathewson et al., 2012; Edgar et al., 2015)?

The final dataset used comprised data from 234 Control and 368 ASD subjects. 5 blocks of eyes open and 5 blocks of eyes closed (2 min duration each) were collected for every subject. Open-eyes and closed-eyes resting state data were analyzed separately, as previous research indicates significant differences in alpha activity between these conditions (Barry et al., 2007).

## Pipeline scripts

- 01_generate_alpha_region_database: Given a database containing alpha EEG parameter (amplitude, n peaks, bandwidth, aperiodic slope and offset) for every channel and every block, this code computes the average value for every parameter in some regions of interest (Frontal, Posteriorior, Central x Right, Left, Midline).
- 02_EEGchannels_Plot&Visualization: this code allows visualizations of parameter values over EEG montage. A visualization is here made for every group. Contrast for eyes open vs. eyes closed are also visualized.
- 03_Statistics_ClosedRestingState: this code performs some preliminary statistic analyses, such as: descriptive statistics, mixed linear model to assess group differences over time on alpha/aper offset parameters. ASD subjects are then clustered based on IQ, and other mixed linear model are performed.
- 04_Statistics_OpenRestingState: this code performs some preliminary statistic analyses, such as: descriptive statistics, mixed linear model to assess group differences over time on alpha/aper offset parameters. ASD subjects are then clustered based on IQ, and other mixed linear model are performed.

## Preliminary Results

No differences between ASD and TD are here found. More promising is the clustering approach, despite clustering solution validation could be potentially improved.

## Installation

Instructions on how to install and set up your project locally.

### Installation Steps

1. Clone the repository:

    ```bash
    git clone https://github.com/username/python-cimec-ines-severino.git
    ```

2. Navigate to the project directory:
    ```bash
    cd python-cimec-ines-severino
    ```
3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Literature

Donoghue T, Haller M, Peterson EJ, Varma P, Sebastian P, Gao R, Noto T, Lara AH, Wallis JD, Knight RT, Shestyuk A, Voytek B. Parameterizing neural power spectra into periodic and aperiodic components. Nat Neurosci. 2020 Dec;23(12):1655-1665. doi: 10.1038/s41593-020-00744-x. Epub 2020 Nov 23. PMID: 33230329; PMCID: PMC8106550.

Ostlund B, Donoghue T, Anaya B, Gunther KE, Karalunas SL, Voytek B, Pérez-Edgar KE. Spectral parameterization for studying neurodevelopment: How and why. Dev Cogn Neurosci. 2022 Apr;54:101073. doi: 10.1016/j.dcn.2022.101073. Epub 2022 Jan 15. PMID: 35074579; PMCID: PMC8792072.

Barry, R. J., Clarke, A. R., Johnstone, S. J., Magee, C. A., & Rushby, J. A. (2007). EEG differences between eyes-closed and eyes-open resting conditions. Clinical Neurophysiology, 118(12), 2765-2773.

Wang, J., Barstein, J., Ethridge, L. E., Mosconi, M. W., Takarae, Y., & Sweeney, J. A. (2013). Resting state EEG abnormalities in autism spectrum disorders. Journal of Neurodevelopmental Disorders, 5(1), 24.

Mathewson, K. J., Jetha, M. K., Drmic, I. E., Bryson, S. E., Goldberg, J. O., & Schmidt, L. A. (2012). Regional EEG alpha power, coherence, and behavioral symptomatology in autism spectrum disorder. Clinical Neurophysiology, 123(9), 1798-1809.

Edgar, J. C., Heiken, K., Chen, Y. H., Herrington, J. D., Chow, V., Liu, S., & Huang, M. (2015). Resting-state alpha rhythms in children with autism spectrum disorder. Journal of Autism and Developmental Disorders, 45(9), 2926-2936.
