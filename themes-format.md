**Theme Definition File Format**

Customizing Doppelgänger requires the use of a themes definition file, containing an array of theme overrides. These override baked-in base themes that provide a suitable starting place for theme development.

Note: This format is in flux and will likely change quite a bit in time as Doppelgänger becomes more readily customized.

**Notes**

Each theme must include a `code`, `parent_code`, and `name`.

The theme's `parent_code` value must be one of the built-in base themes: `default`, `dark`, or `hideous`.

To override a value in the base theme, simply specify it in the theme definition file. Your value will override the base value.

Colors are specified as a string in an RGBA (red, green, blue, alpha) format, as follows: `255,255,255,255`.

Navbar image (`navbar_logo_image`) can be changed by specifying a baked-in image name or a remote URL. Remote URLs should only be used for testing, and the ideal image dimensions should be 450px x 120px.

**Format Reference**

```
[
  {
    "code": "(string, code for theme)",
    "parent_code": "(string, code for theme that is overridden)",
    "name": "(string, visible name)",
    "is_nighttime": (bool, whether this is a 'nighttime' theme),
    "global": {
      "status_bar_style": "(string, status bar style - dark, light)",
      "background_color": "(string, default background color)",
      "buttons": {
        "normal": "(string, default state button color)",
        "highlighted": "(string, highlight state button color)",
        "selected": "(string, selected state button color)",
        "disabled": "(string, disabled state button color)"
      },
      "segmented_controls": {
        "color": "(string, segmented control base color)",
        "text_color_normal": "(string, segmented control text color)",
        "text_color_highlighted": "(string, segmented control text highlight color)",
        "text_color_selected": "(string, segmented control text selected color)",
        "text_color_disabled": "(string, segmented control text disabled color)"
      },
      "switches": {
        "off_color": "(string, switch off color)",
        "on_color": "(string, switch on color)",
        "thumb_color": "(string, switch thumb color)"
      },
      "page_controls": {
        "color": "(string, default page control color)",
        "current_color": "(string, selected page control color)"
      },
      "table_view_cells" : {
        "primary_text_color": "(string, table cell text color)",
        "secondary_text_color": "(string, table cell secondary text color)",
        "background_color": "(string, table cell background color)",
        "background_highlight_color": "(string, table cell highlight color)"
      },
      "loadable_image_background_color": "(string, loadabble image default background color)",
      "primary_text_color": "(string, table cell primary text color)",
      "secondary_text_color": "(string, table cell primary text color)",
      "header_text_color": "(string, table cell header text color)",
      "toolbar_background_color": "(string, toolbar color)",
      "toolbar_style": "(string, toolbar display style - dark, light)",
      "toolbar_is_translucent": (bool, whether toolbar is translucent),
      "picker_item_color": "(string, picker item color)",
      "menu_label_color": "(string, menu item label color)",
      "menu_button_color": "(string, menu item button color)",
      "menu_disclosure_triangle_color": "(string, menu item disclosure triangle color)",
      "menu_checkbox_color": "(string, menu item checkbox color)",
      "mini_progress_track_color": "(string, mini progress track color)",
      "mini_progress_progress_color": "(string, mini progress color)",
      "completion_indicator_color": "(string, completion indicator color)",
      "notifier_visual_effect": "(string, visual effect style for notifier -  extra_light)",
      "table_section_header_visual_effect": "(string, visual effect style for table section headers -  extra_light)",
      "table_section_header_title_color": "(string, table section header text color)",
      "scrollview_indicator_style": "(string, scroll view indicator style - dark, light)",
      "pinstripe_standard_color": "(string, pinstripe standard color)",
      "pinstripe_light_color": "(string, light pinstripe color)",
      "activity_indicator_color": "(string, activity indicator view color)",
      "text_entry_text_color": "(string, text entry text color)",
      "text_entry_background_color": "(string, text entry background color)",
      "text_entry_keyboard_appearance": "(string, keyboard entry style - light, dark)"
    },
    "player_full": {
      "program_name_text_color": "(string, program name text color)",
      "time_values_text_color": "(string, time values text color)",
      "up_next_border_color": "(string, up next border color)",
      "up_next_background_color": "(string, up next background color)",
      "large_top_background_color": "(string, top section background color)",
      "scrubber_track_color": "(string, scrubber track color)",
      "scrubber_loaded_color": "(string, scrubber loaded color)",
      "scrubber_played_color": "(string, scrubber played color)",
      "scrubber_thumb_inactive_color": "(string, scrubber thumb inactive color)",
      "scrubber_thumb_active_color": "(string, scrubber thumb active color)",
      "scrubber_pop_background_color": "(string, pop-up background color)",
      "scrubber_pop_text_color": "(string, pop-up text color)",
      "aux_hint_arrow_color": "(string, auxiliary hint arrow color)"
    },
    "player_mini": {
    },
    "donation": {
      "highlight_background_color": "(string, highlight prompt background color)",
      "option_button_normal_color": "(string, highlight prompt button color)",
      "option_button_highlight_color": "(string, highlight prompt button highlight color)"
    },
    "feedback": {
      "text_entry_background_color": "(string, feedback text entry background color)",
      "text_entry_invalid_background_color": "(string, feedback invalid text entry background color)"
    },
    "articles": {
      "go_to_arrow_color": "(string, go to arrow color)",
      "custom_css": "(string, arbitrary injected css)"
    },
    "schedule": {
      "current_program_color": "(string, current program indicator color)"
    },
    "nav_embedded": {
      "navbar_background_color": "(string, embedded navbar background color)",
      "navbar_button_color": "(string, embedded navbar button color)",
      "navbar_title_color": "(string, embedded navbar title text color)"
    },
    "nav_root": {
      "navbar_logo_image": "(string, nav image as a baked-in image filename or url)",
      "navbar_background_color": "(string, root navbar background color)",
      "navbar_visual_effect": "(string, root navbar style - extra_light, dark)",
      "navbar_title_color": "(string, root navbar title text color)",
      "offline_indicator_background_color": "(string, offline indicator background color)",
      "offline_indicator_text_color": "(string, offline indicator text color)"
    }
  },

  [...]
]
```

**Example Theme Definitions File Content**

```
[
  {
    "code": "default",
    "parent_code": "default",
    "name": "Default Dev",
    "global": {
      "buttons": {
        "normal": "255,0,0,255"
      },
      "segmented_controls": {
        "color": "255,0,0,255",
        "text_color_normal": "255,0,0,255",
        "text_color_highlighted": "170,170,170,255",
        "text_color_selected": "255,255,255,255",
        "text_color_disabled": "170,170,170,255"
      },
      "switches": {
        "off_color": "180,180,180,255",
        "on_color": "190,220,230,255",
        "thumb_color": "255,0,0,255"
      },
      "menu_button_color": "255,0,0,255",
      "menu_disclosure_triangle_color": "255,0,0,255"
    },
    "nav_embedded": {
      "navbar_button_color": "255,0,0,255"
    },
    "nav_root": {
      "navbar_logo_image": "nav_bar_logo.png"
    }
  },


  {
    "code": "dark",
    "parent_code": "dark",
    "name": "Dark Dev",
    "global": {
      "buttons": {
        "normal": "255,0,0,255"
      },
      "segmented_controls": {
        "color": "255,0,0,255",
        "text_color_normal": "255,0,0,255",
        "text_color_highlighted": "170,170,170,255",
        "text_color_selected": "255,255,255,255",
        "text_color_disabled": "170,170,170,255"
      },
      "switches": {
        "off_color": "180,180,180,255",
        "on_color": "190,220,230,255",
        "thumb_color": "255,0,0,255"
      },
      "menu_button_color": "255,0,0,255",
      "menu_disclosure_triangle_color": "255,0,0,255"
    },
    "nav_embedded": {
      "navbar_button_color": "255,0,0,255"
    },
    "nav_root": {
      "navbar_logo_image": "nav_bar_logo_dark.png"
    }
  },


  {
    "code": "hideous",
    "parent_code": "hideous",
    "name": "Hideous Dev",
    "nav_root": {
      "navbar_logo_image": "nav_bar_logo_dark.png"
    }
  }
]
```
