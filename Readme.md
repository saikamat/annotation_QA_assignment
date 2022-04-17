# README

## Phase 1: Task Retrieval
`DONE`

Retrieved tasks using project name "Traffic Sign Detection" and task status "completed"

API used : https://api.scale.com/v1/tasks

Authentication used - Bearer Token - base64 form of "my_api_key:"

## Phase 2: Have `one` interesting/exciting QC
`<TODO>`

## Phase 3: 
### 3.1 Possible QC options:-
1. Largest signs are well annotated
2. High Priority signs are well annotated.
   1. e.g. traffic lights -> non zero `truncation` / `occlusion` or `traffic_light`
   2. `construction_sign`

3. No low-light photos. check `timeofday` tag
4. No photos at curves or roundabouts due to obscurity and poor angles

### 3.2 Places of highest impact:-

Typical Workflow of ML project
`source` / `generate` --> `annotate` --> `manage` / `evaluate` --> `automate`

- Biggest impact of QC is at `source`. 
- Next best option is at `evaluate` and have a feedback loop to `generate`
