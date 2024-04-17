---
layout: page
title: Projects
permalink: /projects/
custom_js: true
---

<div id="tag-selector" class="tags-container">
</div>
<div class="collection-container">
    {% for project in site.data.projects %}
    <div class="collection-item">
        <h3>{{ project.name }}</h3>
        <!-- <div> -->
            <img src="{{ project.cover-photo }}" alt="{{ project.name }}">
        <!-- </div> -->
        <div class="flag">
            {% if project.time %}
            <div>{{ project.time }}</div>
            {% endif %}
            {% if project.team %}
            <div>{{ project.team }}</div>
            {% endif %}
        </div>
        <div>
            {% if project.tags %}
            <div class="tags-container">
                {% for tag in project.tags %}
                <span>{{ tag }}</span>
                {% endfor %}
            </div>
            {% endif %}
            {% if project.description %}
            <div class="desc">
            <p>{{ project.description }}</p>
            </div>
            {% endif %}
            {% if project.url %}
            <span class="link">
                <a href="{{ project.url }}" target="_blank">
                    <span class="fa fa-code"></span>
                </a>
            </span>
            {% endif %}
            {% if project.video %}
            <span class="link">
                <a href="{{ project.video }}" target="_blank">
                    <span class="fa fa-play"></span>
                </a>
            </span>
            {% endif %}
            {% if project.demo-url %}
            <span class="link">
                <a href="{{ project.demo-url }}" target="_blank">
                    <span class="fa fa-laptop"></span>
                </a>
            </span>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>

<script>
    $(document).ready(function() {
        // Obtain the unique text of each tag and insert it into a list
        var tags = [];
        $(".tags-container span").each(function() {
            var tag = $(this).text();
            if (!tags.includes(tag)) {
                tags.push(tag);
            }
        });

        // The list storing selected tags with initial value being all tags
        var selectedTags = [];

        // Insert select all and unselect all buttons into the tag-selector div
        var tagSelector = $("#tag-selector");
        var selectAllButton = $("<button></button>").text("Select All").addClass("functional");
        selectAllButton.click(function() {
            $(".collection-item").show();
            selectedTags = tags.map(tag => tag);
            // add class to all buttons except the functional buttons
            $("#tag-selector button").not(".functional").addClass("selected");
        });

        var unselectAllButton = $("<button></button>").text("Unselect All").addClass("functional");
        unselectAllButton.click(function() {
            $(".collection-item").hide();
            selectedTags = [];
            $("#tag-selector button").not(".functional").removeClass("selected");
        });

        tagSelector.append(selectAllButton);
        tagSelector.append(unselectAllButton);

        // Function to update the display of collection items
        function updateDisplay() {
            $(".collection-item").each(function() {
                var itemTags = $(this).find(".tags-container span");
                var show = false;
                itemTags.each(function() {
                    if (selectedTags.includes($(this).text())) {
                        show = true;
                    }
                });
                if (show) {
                    $(this).show();
                } else {
                    $(this).hide();
                }
            });
        }

        // Insert tag buttons into the tag-selector div
        tags.forEach(function(tag) {
            var button = $("<button></button>").text(tag);
            button.click(function() {
                // change button appearance
                if (selectedTags.includes(tag)) {
                    selectedTags = selectedTags.filter(t => t !== tag);
                    button.removeClass("selected");
                } else {
                    selectedTags.push(tag);
                    button.addClass("selected");
                }
                console.log(selectedTags)

                updateDisplay();
            });
            tagSelector.append(button);
        });
    });
</script>