// RoboLamp Bat-Signal stencil
// All measurements in millimeters.
// Flat stencil — no mounting clips.

$fn = 256;

outer_diameter = 112;
opening_diameter = 102;
thickness = 2;
support_width = 1.6;

bat_outline = [
    [0, 10], [3, 10], [5, 17], [6, 7],
    [12, 5], [20, 7], [29, 12], [40, 20],
    [36, 7], [33, -5], [29, -1], [25, 0],
    [21, -1], [18, -5], [15, -11],
    [12, -6], [9, -5], [6, -7], [0, -20],
    [-6, -7], [-9, -5], [-12, -6],
    [-15, -11], [-18, -5], [-21, -1],
    [-25, 0], [-29, -1], [-33, -5],
    [-36, 7], [-40, 20], [-29, 12],
    [-20, 7], [-12, 5], [-6, 7],
    [-5, 17], [-3, 10]
];

linear_extrude(height = thickness) {
    union() {
        // Outer ring
        difference() {
            circle(d = outer_diameter);
            circle(d = opening_diameter);
        }

        // Solid bat blocks the light
        polygon(points = bat_outline);

        // Thin supports connect the wings to the ring
        translate([28, -support_width / 2])
            square([25, support_width]);

        translate([-53, -support_width / 2])
            square([25, support_width]);
    }
}
