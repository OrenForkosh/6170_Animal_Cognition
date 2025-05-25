# 6170 Animal Cognition Course | HUJI
The data in this repository is based on the experiments used in this study: https://www.nature.com/articles/s41593-019-0516-y
In each experiment, four adult male mice were housed together for four or more days. The arenas were enriched with a closed nest, two feeders, two water bottles, two ramps, an open shelter and an S-shaped separation wall in the center. 

## behaviors_table.csv 
Contains behavioral daily behavioral data

Each row represent one mouse on a specific day of the experiment. Important columns:
1. Day - The day of the experiment (usually between 1 and 4)
2. MouseNumber - Each mouse's unique number
3. MouseID - Each mouse's id within the group (usually between 1 and 4). Note that two mice with the same ID are not the same unless the groupID is also identical.
4. GroupID - the number of the group
5. GroupNumber - avoid using this field and use GroupID instead

In addition to these columns, there are columns that represent specific behaviors or traits. For example: 
1. NormalizedDavidScore - The dominance hieararchy of the mouse on that day
2. AggressiveChaseRateOutside, AggressiveEscapeRateOutside - Rate of aggressive chases or escapes while the mouse is outside the nest

Here is a list of some of the behaviors available:
### Pairwise
- Time outside (1): the fraction of time that the mouse spends outside the nest. Normalizations: total time (%).

- Frequency of visits outside (2): the rate at which the mouse exits the nest. Normalizations: total time (per 1 h).

- Foraging correlation (3): the correlation between the times that the mouse is outside the nest and the times that another mouse is outside the nest, averaged over all mice. For example, the foraging correlation between two mice would equal one if the mouse is always outside the nest when the other mouse is outside, and also enters the nest whenever the other mouse enters the nest. The correlation would be –1 whenever the mouse is outside and the other mouse is inside the nest. Normalizations: (3) none (arbitrary units (a.u.)).

- Contact rate (4, 5): the number of contacts the mouse had. A contact is defined as two mice being less than 10-cm apart while both are outside the nest. Normalizations: (4) total time (per 1 h), (5) time outside (per 1 h).

- Time in contact (6): the fraction of time that a mouse is in contact with other mice while outside the nest. Normalizations: (6) time outside (per 1 h).

- Median/mean contact duration (7, 8): median or mean duration of contacts. The contact duration does not include the times when the mouse approached, moved away from or chased the other mouse. Normalizations: (7, 8) none (s).

- Follow (12, 18, 24): a follow is a contact that ended with one mouse going after another mouse until disengagement. Follows can be either aggressive (chases) or non-aggressive. Normalizations: (12) number of contacts (a.u.), (18) time outside (per 1 h), (24) total time (per 1 h).

- Being followed (13, 19, 25): the number of times a mouse is followed at the end of a contact. It can be either in an aggressive (chases) or non-aggressive manner. Normalizations: (13) number of contacts (a.u.), (19) time outside (per 1 h), (25) total time (per 1 h).

- Chase (10, 16, 22): chases are interactions that ended with the mouse pursuing another mouse in an aggressive manner. Aggressiveness was determined using a classifier that was trained on labeled samples (see Methods). Normalizations: (10) number of contacts (a.u.), (16) time outside (per 1 h), (22) total time (per 1 h).

- Escape (11, 17, 23): the number of time that the mouse was aggressively chased by another mouse. Normalizations: (11) number of contacts (a.u.), (17) time outside (per 1 h), (23) total time (per 1 h).

- Non-aggressive follow (14, 20, 26): the number of times the mouse followed another mouse at the end of a contact in a non-aggressive way. Normalizations: (14) number of contacts (a.u.), (20) time outside (per 1 h), (26) total time (per 1 h).

- Non-aggressively being followed (15, 21, 27): the number of times the mouse was followed by another mouse at the end of a contact in a non-aggressive way. Normalizations: (15) number of contacts (a.u.), (21) time outside (per 1 h), (27) total time (per 1 h).

- Approach (28–32): an approach is a directed movement of the mouse toward another mouse that ends in contact. Not all interactions necessarily start with an approach, while others might start mutually, with both mice approaching each other. Normalizations: (28) none (a.u.), (29) time outside (per 1 h), (30) time outside with one or more mice (per 1 h), (31) number of contacts (a.u.), (32) total (per 1 h).

- Being approached (33–35): the number of times the mouse was approached by another mouse. Normalizations: (33) number of contacts (a.u.), (34) time outside (per 1 h), (35) none (a.u.).

- Approach escape (36): the fraction of contacts in which the mouse initiated the contact and ended up being chased. Normalizations: (36) number of aggressive contacts (a.u.).

- Difference between approaches and chases (9): the total number of chases subtracted from the total number of approaches. Normalizations: (9) none (a.u.).

### Individual
- Region of interest exploration (37, 38): quantifies the amount of exploration the mouse is doing. Measured as the entropy of the probability of being in each of the ten regions-of-interest (ROIs). Mice that spend the same amount of time in all regions will be given the highest score, while mice that spend all their time in a single ROI will be scored zero. When normalized to the time outside, the computation of the entropy also differed by ignoring the probability of being inside the nest. Normalizations: (37) none (bits), (38) time outside (bits h–1).

- Grid exploration (59): quantifies the amount of exploration the mouse is doing. Analogous to ROI exploration, grid exploration was determined using entropy; however, instead of looking at the ROIs, we divided the arena into a 6 × 6 grid (10 ×10 cm; a total of 36 possible locations). Normalizations: (59) none (bits).

- Predictability (60): measures how predictable the paths that the mouse takes as the mutual information between its current and previous location in the arena. For that, the arena was divided into a 6 × 6 grid (10 ×10 cm; a total of 36 possible locations), and for each cell, we computed the probabilities of it moving to any of the adjacent cells. Normalizations: (60) none (bits).

- Distance (58): the total distance traveled by the mouse while outside the nest. To smooth the tracking, the mice locations were sampled once every second. Normalizations: (58) none (m).

- Median/mean speed (54, 55): the median or mean speed while outside the nest. To smooth the computation of the speed, the locations of mice were sampled once every second. Normalizations: (54, 55) none (m s–1).

- Tangential velocity (56): the tangential component of the speed or the part of speed perpendicular to the previous direction of movement. Normalizations: (56) none (m s–1).

- Angular velocity (57): the rate of change in the direction of the mouse. Normalizations: (57) none (rad s–1).

- Food or water (39, 40): the time spent in the feeder or water zones. Normalizations: (39) total time (a.u.), (40) time outside (a.u.).

- Food (41): the time spent next to the feeders. Normalizations: (41) time outside (a.u.).

- Water (42): the time spent next to the water bottles. Normalizations: (42) time outside (a.u.).

- Feeder preference (43): the time spent at (or near) the feeder adjacent to the nest (feeder 1) relative to the farther-away feeder (feeder 2). Normalizations: (43) none (a.u.).

- Water preference (44): time spent near the water bottle adjacent to the nest (water 1) relative to the farther-away water bottle (water 2). Normalizations: (44) none (a.u.).

- Elevated area (45, 46): the time spent on an elevated object in the arena: ramps or block. Normalizations: (45) total time (a.u.), (46) time outside (a.u.).

- Open area (47): the time spent in the open area (outside the nest and in any of the ROIs). Normalizations: (47) time outside (a.u.).

- Shelter (48): the time spent in the shelter, which is a box without a roof and is closed only on its sides. Normalizations: (48) time outside (a.u.).

- Ramps (49): the time spent on the elevated ramps. Normalizations: (49) outside (a.u.).

- S-wall (50): the time spent in the S-wall. Normalizations: (50) time outside (a.u.).

- Distance from walls (51): the average distance from the walls while in the open area. Normalizations: (51) none (cm).

- Distance from nest (52): the average distance from the nest (while outside the nest). Normalizations: (52) none (cm).

- Alone outside (53): the fraction of time the mouse is outside while all other mice are in the nest. Normalizations: (53) total time (a.u.).
