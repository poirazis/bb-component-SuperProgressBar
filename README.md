# Super Progress Bar

A customizable progress bar component for Budibase applications with multiple display modes, styling options, and value formatting.

## 🚀 Features

### Progress Display

- **Multiple Types**: Percentage, value, or progress display modes
- **Value Formatting**: Custom prefixes and suffixes for values
- **Decimal Precision**: Configurable decimal places
- **Range Support**: Custom minimum and maximum values
- **Dynamic Values**: Data-bound progress values

### Visual Customization

- **Size Options**: Small, medium, and large variants
- **Color Control**: Custom progress bar and track colors
- **Label Display**: Optional label text above the progress bar
- **Theme Integration**: Consistent with Budibase design system

### Data Binding

- **Value Binding**: Connect to data sources for dynamic progress
- **Conditional Logic**: Show/hide based on data conditions
- **Real-time Updates**: Automatic updates as data changes
- **Expression Support**: Calculated progress values

### User Experience

- **Visual Feedback**: Clear progress indication
- **Accessibility**: Screen reader support and ARIA labels
- **Responsive Design**: Adapts to different screen sizes
- **Performance**: Efficient rendering for dynamic updates

## 📝 Usage Instructions

### Basic Setup

1. Add the Super Progress Bar component to your screen
2. Set the progress type (percentage, value, or progress)
3. Configure the value source (static or data-bound)
4. Customize colors and size as needed

### Advanced Configuration

- **Value Formatting**: Add prefixes/suffixes for context
- **Range Settings**: Define min/max values for calculations
- **Decimal Places**: Set precision for numeric displays
- **Color Theming**: Match your application's color scheme

### Common Use Cases

- **Task Completion**: Show percentage of completed tasks
- **Loading States**: Display loading or processing progress
- **Goal Tracking**: Visualize progress toward targets
- **Survey Results**: Show completion percentages
- **File Upload**: Display upload progress
- **Performance Metrics**: Show KPI progress indicators

## 🔧 Configuration Options

| Setting      | Type          | Description                              |
| ------------ | ------------- | ---------------------------------------- |
| Label        | String        | Display label text                       |
| Type         | Select        | Display mode (percentage/value/progress) |
| Value        | Number/String | Progress value or expression             |
| Value Prefix | String        | Text before value (non-percentage)       |
| Value Suffix | String        | Text after value (non-percentage)        |
| Min Value    | Number        | Minimum range value                      |
| Max Value    | Number        | Maximum range value                      |
| Decimals     | Number        | Decimal precision                        |
| Size         | Select        | Bar size (small/medium/large)            |
| Color        | Color         | Progress bar color                       |
| Track Color  | Color         | Background track color                   |

## 🎨 Styling

The component supports Budibase's styling system with:

- **Color Customization**: Full color control for bar and track
- **Size Variants**: Three size options for different contexts
- **Theme Consistency**: Matches application design language
- **Custom CSS**: Advanced styling modifications

## 🔍 Best Practices

- Use percentage mode for completion indicators
- Choose appropriate colors for different progress states
- Set meaningful min/max values for value ranges
- Consider decimal precision for accuracy vs. readability
- Use labels to provide context for the progress
- Test color contrast for accessibility
