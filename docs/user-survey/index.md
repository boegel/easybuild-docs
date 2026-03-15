# EasyBuild User Survey

The results of the EasyBuild User Survey are assumed to give a fairly representative view
on the EasyBuild community, but they should be interpreted with a grain of salt,
since there is no doubt significant bias in terms of participants.

<figure markdown="span">
![Sampling bias cartoon](img/sampling-bias.png){: align=center style="width:350px"}
</figure>

---

## Survey participation

### Number of participants

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Number of participants to EasyBuild User Survey",
  "data": {
    "values": [
      {"year": "2017", "value": 77},
      {"year": "2018", "value": 92},
      {"year": "2019", "value": 88},
      {"year": "2020", "value": 94},
      {"year": "2021", "value": 105},
      {"year": "2022", "value": 118},
      {"year": "2023", "value": 108},
      {"year": "2024", "value": 117},
      {"year": "2025", "value": 1000, "type": "last"}
    ]
  },
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {"field": "year"},
    "y": {"field": "value", "type": "quantitative", "title": "number of participants"},
    "color": {
      "condition": {
        "test": "datum['type'] == 'last'",
        "value": "green"
      }
    }
  }
}
```

### Returning vs new participants

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Have you participated in the EasyBuild User Survey before? *(one answer per participant)*",
  "data": {
    "values": [
      {"year": "2023", "answer": "Yes, all since 2017",             "order": 1, "count": 16},
      {"year": "2023", "answer": "Yes, some but not all",           "order": 2, "count": 46},
      {"year": "2023", "answer": "Yes, only last one",              "order": 3, "count": 4},
      {"year": "2023", "answer": "No, did not participate",         "order": 4, "count": 10},
      {"year": "2023", "answer": "No, did not know about it",       "order": 5, "count": 32},

      {"year": "2024", "answer": "Yes, all since 2017",             "order": 1, "count": 13},
      {"year": "2024", "answer": "Yes, some but not all",           "order": 2, "count": 55},
      {"year": "2024", "answer": "Yes, only last one",              "order": 3, "count": 15},
      {"year": "2024", "answer": "No, did not participate",         "order": 4, "count": 10},
      {"year": "2024", "answer": "No, did not know about it",       "order": 5, "count": 26},

      {"year": "2025", "answer": "Yes, all since 2017",             "order": 1, "count": 1},
      {"year": "2025", "answer": "Yes, some but not all",           "order": 2, "count": 1},
      {"year": "2025", "answer": "Yes, only last one", "order": 3,  "count": 1},
      {"year": "2025", "answer": "No, did not participate",         "order": 4, "count": 1},
      {"year": "2025", "answer": "No, did not know about it",       "order": 5, "count": 1}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {"field": "year"},
    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },
    "xOffset": {
      "field": "answer",
      "sort": {"field": "order"}
    },
    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "Yes, all since 2017",
          "Yes, some but not all",
          "Yes, only last one",
          "No, did not participate",
          "No, did not know about it"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "orange", "red"]
      },
      "legend": {
        "title": "",
        "labelFontSize": 12
      }
    }
  }
}
```

### Channel

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Via which channel did you become aware of this EasyBuild User Survey?",
  "data": {
    "values": [
      {"year": "2023", "answer": "EasyBuild mailing list",      "order": 1,  "count": 35},
      {"year": "2023", "answer": "EasyBuild Slack",             "order": 2,  "count": 54},
      {"year": "2023", "answer": "EasyBuild website",           "order": 3,  "count": 3},
      {"year": "2023", "answer": "Conference or event",         "order": 4,  "count": 0},
      {"year": "2023", "answer": "Twitter",                     "order": 5,  "count": 2},
      {"year": "2023", "answer": "Mastodon",                    "order": 6,  "count": 1},
      {"year": "2023", "answer": "BlueSky",                     "order": 7,  "count": 0},
      {"year": "2023", "answer": "LinkedIn",                    "order": 8,  "count": 1},
      {"year": "2023", "answer": "Someone mentioned it to me",  "order": 9,  "count": 9},
      {"year": "2023", "answer": "(other)",                     "order": 10, "count": 3},

      {"year": "2024", "answer": "EasyBuild mailing list",      "order": 1,  "count": 42},
      {"year": "2024", "answer": "EasyBuild Slack",             "order": 2,  "count": 62},
      {"year": "2024", "answer": "EasyBuild website",           "order": 3,  "count": 4},
      {"year": "2024", "answer": "Conference or event",         "order": 4,  "count": 0},
      {"year": "2024", "answer": "Twitter",                     "order": 5,  "count": 0},
      {"year": "2024", "answer": "Mastodon",                    "order": 6,  "count": 0},
      {"year": "2024", "answer": "BlueSky",                     "order": 7,  "count": 0},
      {"year": "2024", "answer": "LinkedIn",                    "order": 8,  "count": 1},
      {"year": "2024", "answer": "Someone mentioned it to me",  "order": 9,  "count": 8},
      {"year": "2024", "answer": "(other)",                     "order": 10, "count": 2},

      {"year": "2025", "answer": "EasyBuild mailing list",      "order": 1,  "count": 1},
      {"year": "2025", "answer": "EasyBuild Slack",             "order": 2,  "count": 1},
      {"year": "2025", "answer": "EasyBuild website",           "order": 3,  "count": 1},
      {"year": "2025", "answer": "Conference or event",         "order": 4,  "count": 1},
      {"year": "2025", "answer": "Twitter",                     "order": 5,  "count": 1},
      {"year": "2025", "answer": "Mastodon",                    "order": 6,  "count": 1},
      {"year": "2025", "answer": "BlueSky",                     "order": 7,  "count": 1},
      {"year": "2025", "answer": "LinkedIn",                    "order": 8,  "count": 1},
      {"year": "2025", "answer": "Someone mentioned it to me",  "order": 9,  "count": 1},
      {"year": "2025", "answer": "(other)",                     "order": 10, "count": 1}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {
        "field": "year",
        "labelFontSize": 12
    },
    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },
    "xOffset": {
      "field": "answer",
      "sort": {"field": "order"}
    },
    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "EasyBuild mailing list",
          "EasyBuild Slack",
          "EasyBuild website",
          "Conference or event",
          "Twitter",
          "Mastodon",
          "BlueSky",
          "LinkedIn",
          "Someone mentioned it to me",
          "(other)"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "purple", "red", "orange", "yellow", "pink", "darkblue", "gray"]
      },
      "legend": {
        "title": "",
        "labelFontSize": 12
      }
    }
  }
}
```

---

## Demographics

### Primary profile

***Q2. What is your primary profile?***

### Type of organisation

***Q3. What type of organisation do you work for?***

### Part of the world

***Q4. In which part of the world are you located?***

---

## EasyBuild: adoption and experience

***Q5. How long have you been using EasyBuild?***

***Q6. How did you first learn about EasyBuild?***

***Q7. What is the main aspect of EasyBuild that convinced you to start using it?***

## Operating system

***Q8. On which operating system(s) do you use EasyBuild
(most commonly, so pick one)?***

## Python version

***Q9. Which Python version do you usually use to run EasyBuild?
(check with "eb --show-system-info")
(note: this is *not* about which Python versions you install *with* EasyBuild)***

***Q10. How troublesome has it been for you that EasyBuild became incompatible with Python 2.7?
Support for running EasyBuild with Python 2.7 was removed in EasyBuild v5.0.0 (released March 2025)***

***Q11. How troublesome would it be for you if EasyBuild becomes incompatible with Python versions older than Python 3.9?
Support for running EasyBuild with Python < 3.9 was deprecated in EasyBuild v5.2.0 (released Dec 2025), and is planned to be removed in EasyBuild 6.0.0 (planned for release in Spring 2027). Python 3.9 has been officially end-of-life since 31 Oct 2025.***

***Q12. How troublesome would it be for you if EasyBuild becomes incompatible with Python versions older than Python 3.12?
Removing support for running EasyBuild with Python < 3.12 is currently being considered for EasyBuild 6.0.0 (planned for release in Spring 2027)***

## System aspects

### CPUs

***Q13. What's the aggregate CPU core count for the HPC systems you manage, support, or use?***

***Q14. Are you installing software optimized for different CPU types?***

***Q15. For which CPU types are you installing software using EasyBuild?***

### GPUs

***Q16. What's the aggregate GPU count for the HPC systems you manage, support, or use?***

***Q17. Are you installing software optimized for different GPU types?***

***Q18. For which accelerators are you installing software using EasyBuild?***

### Top500

***Q19. Are you using EasyBuild on a system that's in the current Top500 list (Nov'25)?
(see https://top500.org/lists/top500/list/2025/11)***

## EasyBuild installaiton & version

***Q20. How do you usually install EasyBuild itself?***

***Q21. Which EasyBuild version do you mainly use?
(check with "eb --version")***

***Q22. If you're not using the latest release, why not?***

## Toolchains

***Q23. Which (full) toolchain(s) do you use?
(foss entries include GCC + gompi + gfbf subtoolchains)
(intel entries include intel-compilers + iimpi + iimkl subtoolchains)***

***Q24. How frequently should the 'foss' and 'intel' common toolchains be updated?
The frequency for defining new common toolchain versions have been revised early 2026.
We will now strive towards having about 1 toolchain per year, the versioning scheme for upcoming common toolchain versions has been changed to <year>.<number> (like 2026.1).***

## Software installations

***Q25. How many software installations did you perform in the last year (2025) using EasyBuild?***

***Q26. How many software installations/modules installed with EasyBuild do you currently have in production?
(in total, across different systems)***

***Q27. Is EasyBuild your only way of installing (scientific) software?***

***Q28. Do you still install (scientific) software manually?***

***Q29. Are end users using EasyBuild to install software in their own accounts, or are you doing so yourself?***

## Customizations

***Q30. Which easyconfig files do you use?***

***Q31. Do you use any custom easyblocks not included in the central EasyBuild repository?***

***Q32. Have you made any site-specific customisations to EasyBuild?***

## Community

***Q33. Do you actively contribute back to EasyBuild?***

***Q34. Are you subscribed to the EasyBuild mailing list?
(if not, you can subscribe via https://lists.ugent.be/sympa/subscribe/easybuild)***

***Q35. Do you use the EasyBuild Slack?
(if not, you can self-request a Slack invite via https://easybuild.io/join-slack)***

***Q36. Are you planning to attend the next EasyBuild User Meeting?
(21-23 April 2026 @ Guimarães, Portugal, see https://easybuild.io/eum)?***

## Logo

***Q37. How do you like the updated EasyBuild logo (since Nov'22)?
(see also https://easybuild.io/new-logo-2022.html)***

## Documentation

***Q38. How complete is the EasyBuild documentation according to you?***

***Q39. How well organised is the EasyBuild documentation according to you?***

***Q40. How often do you consult the EasyBuild documentation?***

***Q41. How useful is the EasyBuild documentation to you?***

## Tutorial

***Q42. Are you aware of the EasyBuild tutorial?
(see https://tutorial.easybuild.io)***

***Q43. Have you worked through the EasyBuild tutorial?***

## Other tools & projects

***Q44. Do you use any other tools/projects in combination with EasyBuild?***

## EasyBuild features

***Q45. What are your favourite EasyBuild features?***

## Environment Modules

***Q46. How long are modules installed with EasyBuild available to users?***

***Q47. Which module naming scheme do you use?
(see also https://tutorial.easybuild.io/2023-eb-eessi-uk-workshop/easybuild-module-naming-schemes/)***

## Other aspects of EasyBuild

***Q48. How do you like the frequency of EasyBuild releases?
in 2020: 8 in total (2 feature release + 6 bug fix/update release);
in 2021: 7 in total (2 feature releases + 5 bug fix/update releases);
in 2022: 7 in total (1 feature release + 6 bug fix/update releases);
in 2023: 7 in total (3 feature releases + 4 bug fix/update releases);
in 2024: 4 in total (4 bug fix/update releases);
in 2025: 5 in total (1 major release + 2 feature releases + 2 bugfix/update releases);***

***Q49. Which parts of EasyBuild do you not like?***

***Q50. If a commercial support option would be available, would you consider purchasing it?
(note: purely informative, no plans in that direction currently by the core EasyBuild team)***

## EESSI

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Have you heard about the EESSI project?",
  "width": 500,
  "data": {
    "values": [
      {"year": 2022, "answer": "Yes, really interesting",               "count": 27},
      {"year": 2022, "answer": "Yes, have not played with it yet",      "count": 38},
      {"year": 2022, "answer": "Only vague notion of it",               "count": 13},
      {"year": 2022, "answer": "Heard about it, not sure what it is",   "count": 9},
      {"year": 2022, "answer": "No idea what it is",                    "count": 30},

      {"year": 2023, "answer": "Yes, really interesting",               "count": 34},
      {"year": 2023, "answer": "Yes, have not played with it yet",      "count": 41},
      {"year": 2023, "answer": "Only vague notion of it",               "count": 11},
      {"year": 2023, "answer": "Heard about it, not sure what it is",   "count": 8},
      {"year": 2023, "answer": "No idea what it is",                    "count": 14},
    
      {"year": 2024, "answer": "Yes, really interesting",               "count": 42},
      {"year": 2024, "answer": "Yes, have not played with it yet",      "count": 50},
      {"year": 2024, "answer": "Only vague notion of it",               "count": 14},
      {"year": 2024, "answer": "Heard about it, not sure what it is",   "count": 2},
      {"year": 2024, "answer": "No idea what it is",                    "count": 12},
    
      {"year": 2025, "answer": "Yes, really interesting",               "count": 1},
      {"year": 2025, "answer": "Yes, have not played with it yet",      "count": 1},
      {"year": 2025, "answer": "Only vague notion of it",               "count": 1},
      {"year": 2025, "answer": "Heard about it, not sure what it is",   "count": 1},
      {"year": 2025, "answer": "No idea what it is",                    "count": 1}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {
    "type": "line",
    "point": {"size": 50, "shape": "circle"},
    "tooltip": true
  },

  "encoding": {
    "x": {
      "field": "year",
      "type": "ordinal"
    },

    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },

    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "Yes, really interesting",
          "Yes, have not played with it yet",
          "Only vague notion of it",
          "Heard about it, not sure what it is",
          "No idea what it is"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "orange", "red"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```

***Q52. Is EESSI available on the HPC systems you use?
(check with "ls /cvmfs/software.eessi.io", see also https://eessi.io/docs/getting_access/is_eessi_accessible + https://eessi.io/docs/systems/)?***

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Is EESSI available on the HPC systems you use?  PARTIAL DATA 20260314",
  "width": 500,
  "data": {
    "values": [
      {"year": 2024, "answer": "Yes, on each system I use",           "count": 12},
      {"year": 2024, "answer": "Yes, on most systems I use",          "count": 6},
      {"year": 2024, "answer": "Yes, on some systems I use",          "count": 15},
      {"year": 2024, "answer": "Yes, but only by exception",          "count": 6},
      {"year": 2024, "answer": "No, not on any of the systems I use", "count": 82},

      {"year": 2025, "answer": "Yes, on each system I use",           "count": 6},
      {"year": 2025, "answer": "Yes, on most systems I use",          "count": 2},
      {"year": 2025, "answer": "Yes, on some systems I use",          "count": 6},
      {"year": 2025, "answer": "Yes, but only by exception",          "count": 1},
      {"year": 2025, "answer": "No, not on any of the systems I use", "count": 12}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {
    "type": "line",
    "point": {"size": 50, "shape": "circle"},
    "tooltip": true
  },

  "encoding": {
    "x": {
      "field": "year",
      "type": "ordinal"
    },

    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },

    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "Yes, on each system I use",
          "Yes, on most systems I use",
          "Yes, on some systems I use",
          "Yes, but only by exception",
          "No, not on any of the systems I use"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "orange", "red"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```


## AI / LLMs

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Are you using AI tooling (like LLMs)? PARTIAL RESULTS 20260314",
  "data": {
    "values": [

      {"year": "2025", "answer": "Yes, in general (non-EasyBuild)",  "order": 1,   "count": 17},
      {"year": "2025", "answer": "Yes, easyconfig files",            "order": 2,   "count": 9},
      {"year": "2025", "answer": "Yes, easyblocks",                  "order": 3,   "count": 2},
      {"year": "2025", "answer": "Yes, EasyBuild framework",         "order": 4,   "count": 0},
      {"year": "2025", "answer": "Yes, EasyBuild hooks",             "order": 5,   "count": 2},
      {"year": "2025", "answer": "Yes, EasyBuild docs",              "order": 6,   "count": 0},
      {"year": "2025", "answer": "No, but would like to start",      "order": 7,   "count": 2},
      {"year": "2025", "answer": "No, not planning to",              "order": 8,   "count": 5},
      {"year": "2025", "answer": "I am an AI agent ",                "order": 9,   "count": 1},
      {"year": "2025", "answer": "Other",                            "order": 10,  "count": 2},
      {"year": "2025", "answer": "TOTAL_PARTICIPANTS_FOR_THIS_YEAR", "order": 0,   "count": 27}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "max",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"},
    {"filter": "datum.answer != 'TOTAL_PARTICIPANTS_FOR_THIS_YEAR'"}
  ],
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {
        "field": "year",
        "labelFontSize": 12
    },
    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },
    "xOffset": {
      "field": "answer",
      "sort": {"field": "order"}
    },
    "color": {
      "field": "answer",
      "scale": {
        "domain": [
            "Yes, in general (non-EasyBuild)",
            "Yes, easyconfig files",
            "Yes, easyblocks",
            "Yes, EasyBuild framework",
            "Yes, EasyBuild hooks",
            "Yes, EasyBuild docs",
            "No, but would like to start",
            "No, not planning to",
            "I am an AI agent ",
            "Other"
        ],
        "range": ["#4682b4", "darkgreen", "lightgreen", "orange", "yellow", "darkblue", "purple", "red", "pink", "gray"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "Are you interested in features that integrate LLMs with EasyBuild? PARTIAL RESULTS 20260314",
  "data": {
    "values": [

      {"year": "2025", "answer": "Yes, already doing so",            "order": 1,   "count": 0},
      {"year": "2025", "answer": "Yes, interested",                  "order": 2,   "count": 10},
      {"year": "2025", "answer": "Maybe, depends on what it does",   "order": 3,   "count": 12},
      {"year": "2025", "answer": "No, not interested",               "order": 4,   "count": 5},
      {"year": "2025", "answer": "Other",                            "order": 5,   "count": 0},
      {"year": "2025", "answer": "TOTAL_PARTICIPANTS_FOR_THIS_YEAR", "order": 0,   "count": 27}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "max",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"},
    {"filter": "datum.answer != 'TOTAL_PARTICIPANTS_FOR_THIS_YEAR'"}
  ],
  "mark": {
    "type": "bar",
    "tooltip": true
  },
  "encoding": {
    "x": {
        "field": "year",
        "labelFontSize": 12
    },
    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },
    "xOffset": {
      "field": "answer",
      "sort": {"field": "order"}
    },
    "color": {
      "field": "answer",
      "scale": {
        "domain": [
            "Yes, already doing so",
            "Yes, interested",
            "Maybe, depends on what it does",
            "No, not interested",
            "Other"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "red", "gray"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```

## Overall

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "title": "How would you rate the overall quality of EasyBuild?",
  "width": 200,
  "height": 200,
  "data": {
    "values": [
      {"answer": "Excellent", "count": 60},
      {"answer": "Great", "count": 54},
      {"answer": "OK", "count": 6},
      {"answer": "Could be better", "count": 1},
      {"answer": "Pretty bad", "count": 0}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {"type": "arc", "tooltip": true},
  "encoding": {
    "theta": {
      "field": "value",
      "type": "quantitative"
    },
    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "Excellent",
          "Great",
          "OK",
          "Could be better",
          "Pretty bad"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "orange", "red"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v6.json",
  "width": 500,
  "data": {
    "values": [
      {"year": 2017, "answer": "Excellent",       "count": 28},
      {"year": 2017, "answer": "Great",           "count": 40},
      {"year": 2017, "answer": "OK",              "count": 9},
      {"year": 2017, "answer": "Could be better", "count": 0},
      {"year": 2017, "answer": "Pretty bad",      "count": 0},

      {"year": 2018, "answer": "Excellent",       "count": 31},
      {"year": 2018, "answer": "Great",           "count": 50},
      {"year": 2018, "answer": "OK",              "count": 11},
      {"year": 2018, "answer": "Could be better", "count": 0},
      {"year": 2018, "answer": "Pretty bad",      "count": 0},

      {"year": 2019, "answer": "Excellent",       "count": 28},
      {"year": 2019, "answer": "Great",           "count": 53},
      {"year": 2019, "answer": "OK",              "count": 8},
      {"year": 2019, "answer": "Could be better", "count": 2},
      {"year": 2019, "answer": "Pretty bad",      "count": 0},

      {"year": 2020, "answer": "Excellent",       "count": 45},
      {"year": 2020, "answer": "Great",           "count": 42},
      {"year": 2020, "answer": "OK",              "count": 4},
      {"year": 2020, "answer": "Could be better", "count": 2},
      {"year": 2020, "answer": "Pretty bad",      "count": 0},

      {"year": 2021, "answer": "Excellent",       "count": 50},
      {"year": 2021, "answer": "Great",           "count": 48},
      {"year": 2021, "answer": "OK",              "count": 5},
      {"year": 2021, "answer": "Could be better", "count": 1},
      {"year": 2021, "answer": "Pretty bad",      "count": 0},

      {"year": 2022, "answer": "Excellent",       "count": 52},
      {"year": 2022, "answer": "Great",           "count": 57},
      {"year": 2022, "answer": "OK",              "count": 7},
      {"year": 2022, "answer": "Could be better", "count": 1},
      {"year": 2022, "answer": "Pretty bad",      "count": 0},

      {"year": 2023, "answer": "Excellent",       "count": 45},
      {"year": 2023, "answer": "Great",           "count": 51},
      {"year": 2023, "answer": "OK",              "count": 11},
      {"year": 2023, "answer": "Could be better", "count": 1},
      {"year": 2023, "answer": "Pretty bad",      "count": 0},

      {"year": 2024, "answer": "Excellent",       "count": 60},
      {"year": 2024, "answer": "Great",           "count": 54},
      {"year": 2024, "answer": "OK",              "count": 6},
      {"year": 2024, "answer": "Could be better", "count": 1},
      {"year": 2024, "answer": "Pretty bad",      "count": 0},

      {"year": 2025, "answer": "Excellent",       "count": 0},
      {"year": 2025, "answer": "Great",           "count": 0},
      {"year": 2025, "answer": "OK",              "count": 0},
      {"year": 2025, "answer": "Could be better", "count": 0},
      {"year": 2025, "answer": "Pretty bad",      "count": 0}
    ]
  },
  "transform": [
    {"joinaggregate": [{
        "op": "sum",
        "field": "count",
        "as": "total_count"
      }],
      "groupby": ["year"]
    },
    {"calculate": "100*datum.count/datum.total_count", "as": "value"}
  ],
  "mark": {
    "type": "line",
    "point": {"size": 50, "shape": "circle"},
    "tooltip": true
  },

  "encoding": {
    "x": {
      "field": "year",
      "type": "ordinal"
    },

    "y": {
      "field": "value",
      "type": "quantitative",
      "title": "% of participants",
      "axis": {
         "format": ".1f",
         "labelExpr": "datum.value + '%'"
      }
    },

    "color": {
      "field": "answer",
      "scale": {
        "domain": [
          "Excellent",
          "Great",
          "OK",
          "Could be better",
          "Pretty bad"
        ],
        "range": ["darkgreen", "lightgreen", "#4682b4", "orange", "red"]
      },
      "legend": {
        "title": "",
        "labelLimit": 200,
        "labelFontSize": 12
      }
    }
  }
}
```

## Open questions

**Q56. Do you have any suggestions for additional features?**

**Q57. Any additional comments?**
