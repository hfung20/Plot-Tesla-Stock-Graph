# Plot-Tesla-Stock-Graph
Plot Tesla Stock Graph
def make_graph(tesla_data, tesla_revenue, 'Tesla'):
    fig = make_subplots(rows=2, cols=1, shared_xaxes=True, subplot_titles=("Historical Share Price", "Historical Revenue"), vertical_spacing = .3)
    tesla_data_specific = tesla_data[tesla_data.Date <= '2021-06-30']
    tesla_revenue_specific = tesla_revenue[revenue_data.Date <= '2021-06-30']
    fig.add_trace(go.Scatter(x=pd.to_datetime(tesla_data_specific.Date, infer_datetime_format=True), y=tesla_data_specific.Close.astype("float"), name="Share Price"), row=1, col=1)
    fig.add_trace(go.Scatter(x=pd.to_datetime(tesla_revenue_specific.Date, infer_datetime_format=True), y=tesla_revenue_specific.Revenue.astype("float"), name="Revenue"), row=2, col=1)
    fig.update_xaxes(title_text="Date", row=1, col=1)
    fig.update_xaxes(title_text="Date", row=2, col=1)
    fig.update_yaxes(title_text="Price ($US)", row=1, col=1)
    fig.update_yaxes(title_text="Revenue ($US Millions)", row=2, col=1)
    fig.update_layout(showlegend=False,
    height=900,
    title=stock,
    xaxis_rangeslider_visible=True)
    fig.show()
    from IPython.display import display, HTML
    fig_html = fig.to_html()
    display(HTML(fig_html))
