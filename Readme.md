# README: Automated Quality Check (QC) for Traffic Signs

## Scope of the Assignment
- The results of the assignments are limited by the quality and quantity of data available to the applicant. For instance, only the data available in the JSON format after retrieving a certain task is used for the QC.
- If more data were available in the aforementioned JSON, then potentially better QC is always possible. For instance, if `image_metadata` attributes such as `date_time` or even `tags`, were available, then images taken after sunset could be rejected due to poorer quality of annotations.

## Running the code
### Prerequisites
1. In a virtual environment, install the following:-
```
pip install requests
pip install json
pip install os
pip install python3
pip3 install jupyter
pip install -U jupyter
```
2. Start the notebook server from the command line:-
```
jupyter notebook
```
You should see the notebook open in your browser.

----
## Phase 1: Task Retrieval
`DONE`

Retrieved tasks using project name `Traffic Sign Detection` and task status `Completed`

API used : https://api.scale.com/v1/

Authentication used - Bearer Token - base64 form of `my_api_key`

----
## Phase 2: Have `one` interesting/exciting QC
`DONE`

To maintain consistency in labelling, annotation rules states __`background_color` as `not_applicable` should be used only for the `non_visible_face` label__.

The implemented QC makes sure that this convention is followed. 

----
## Phase 3: Reflection on Future Quality Checks
`DONE`
### 3.1 Other Potential QCs:-
1. Largest signs are well annotated. i.e compare an annotation to the image resolution. Pick the top 5 largest annotations, and make sure they have enough information.
2. High Priority signs are well annotated.
   1. e.g. traffic lights -> non zero `truncation` / `occlusion` or `traffic_light`
   2. `construction_sign`

3. No low-light photos. check `timeofday` tag
4. No photos at curves or roundabouts due to obscurity and poor angles

### 3.2 Places of highest impact:-

Typical Workflow of ML project
`source` / `generate` --> `annotate` --> `manage` / `evaluate` --> `automate`

- Biggest impact of QC is at `source`.
- Next best option is at `annotate` stage.
- 3rd best option is at `evaluate` and have a feedback loop to `generate`.
